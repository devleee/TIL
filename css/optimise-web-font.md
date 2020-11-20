# Obtimise Web Font
> Web fonts allow Web designers to use fonts that are not installed on the user's computer. The font file in the server will be downloaded to the user when needed. But problems occur when the font hasn't downloaded yet. If the font is not yet available, some browsers do not render any text.

### Solution 1. Make the font file smaller
- WOFF is more compressed than EOT and TTF. WOFF2 is even more compressed. But to support all browsers you may need more than one font format. (WOFF2 is not supported in IE, WOFF is not supported in some older browsers and Opera Mini)
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
### Solution 2. Make the text always visible
- `font-display`
  - `font-display: block` : Gives the font face a short block period and an infinite swap period. The text content is not visible (for maximum 3s) before the web font is loaded.
  - `font-display: swap` : Gives the font face an extremely small block period and an infinite swap period. Fallback font is used to render the content before the web font is loaded. Once the font file is loaded, swap the fonts.
  - `font-display: fallback` : Gives the font face an extremely small block period and a short swap period. Render the text with the fallback font and if the font is loaded within swap period(2s), swap the fonts. If not, swap does not occur but the font file is saved in the cache.
  - `font-display: optional` : Gives the font face an extremely small block period and no swap period. Similar to `fallback` but the swap occurs depending on the network status.

### Solution 3. Preload the font file
- Use `rel="preload"` in `<link>`
  ```css
  <link rel="preload">
  ```
