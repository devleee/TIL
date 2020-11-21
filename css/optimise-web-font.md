# Optimise Web Font
> Web fonts allow Web designers to use fonts that are not installed on the user's computer. The font file in the server will be downloaded to the user when needed. But problems occur when the font hasn't downloaded yet. If the font is not yet available, some browsers do not render any text (FOIT : Flash Of Invisible Text).

### Solution 1. Make the font file smaller
1. WOFF is more compressed than EOT and TTF. WOFF2 is even more compressed. But to support all browsers you may need more than one font format. (WOFF2 is not supported in IE, WOFF is not supported in some older browsers and Opera Mini)
  - Example : 
    ```css
    @font-face {
      font-family: 'SomeFont';
      src: url('/fonts/SomeFont.woff2') format('woff2'), 
          url('/fonts/SomeFont.woff') format('woff'),
          url('/fonts/SomeFont.ttf') format('truetype');
      /* ttf is used as a fallback in case the browser does not support neither woff2 nor woff */
    }
    ```
2. Consider **font subsetting**.
- Font subsetting : Process of making the font file smaller by removing unnecessary characters.
- Font subsetting tool : [glyphhanger](https://github.com/filamentgroup/glyphhanger)
3. Consider using `unicode-range`
- `unicode-range` : Defines the specific range of the characters that are used with fonts specified by the `@font-face` property for the use on the current page. If the page does not use a character in the range, the font is not downloaded. If at least one character is used, the whole font is downloaded (download the font only when it's needed in the page).
    ```css
    @font-face {
      font-family: 'Nanum Gothic';
      src: url('/fonts/NanumGothicRegular.woff2') format('woff2'), 
           url('/fonts/NanumGothicRegular.woff') format('woff');
           unicode-range: U+AC00-D7A3;
      /* Download Nanum Gothic only when the text content of the page contains Hangul characters*/
    }
    ```
4. Consider using a **variable font**.
-  Variable font : let you access the entire range of weights, widths, and styles in a given font file via CSS and a single @font-face reference. (Not supported in IE)
    ```css
    @font-face {
      font-family: 'Source Sans';
      src: url('/fonts/SourceSansVariable.woff2') format("woff2-variations");
      font-weight: 1 999;
    }

    html {
      font-family: 'SourceSans', sans-serif;
    }

    .text-bold { font-weight: 700; }
    .text-normal { font-weight: 400; }
    .text-light {font-weight: 300;}
    ```
### Solution 2. Make the text always visible
- `font-display`
  - `font-display: block` : Gives the font face a short block period and an infinite swap period. The text content is not visible (for maximum 3s) before the web font is loaded.
  - `font-display: swap` : Gives the font face an extremely small block period and an infinite swap period. Fallback font is used to render the content before the web font is loaded. Once the font file is loaded, swap the fonts.
  - `font-display: fallback` : Gives the font face an extremely small block period and a short swap period. Render the text with the fallback font and if the font is loaded within swap period(2s), swap the fonts. If not, swap does not occur but the font file is saved in the cache.
  - `font-display: optional` : Gives the font face an extremely small block period and no swap period. Similar to `fallback` but the swap occurs depending on the network status.

### Solution 3. Preload the font file
- Use `rel="preload"` in `<link>`
  ```html
  <link rel="preload" href="fonts/SomeFont.woff2" as="font" type="font/woff2" crossorigin>
  ```
