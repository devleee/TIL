# Background

> Shorthand CSS property sets different background properties in one declaration, such as color, image, position, size, and repeat method.

- Syntax : `background: bg-color bg-image position/bg-size bg-repeat bg-origin bg-clip bg-attachment initial|inherit;`
  ```css
  .bg { 
    background: lightcyan url(https://picsum.photos/id/1040/200/300) center/contain no-repeat border-box border-box scroll;
  }
  ```
- Any property you don’t specify in the background property is automatically set to its default.
  ```css
  .bg {
    background-color: lightcyan;
    background: url(https://picsum.photos/id/1040/200/300);
  }
  /* 
  result
    background-color: transparent(default);
    background-image: url(https://picsum.photos/id/1040/200/300); 
  */
  ```

### Background Properties
[background properties example](https://codepen.io/devleee/pen/RwROOpE)
- `background-color` : Sets the background color of an element. HEX, RGB, RGBa, HSL, HSLa and [140 color names](https://www.w3schools.com/colors/colors_groups.asp) can be used.
- `background-image` : Set one or more background images on an element. url of an image and linear/radial gradients can be used.
- `background-position` : Specify the starting position of a background image.
- `background-size` : Set the size of a background-image.
- `background-repeat` : Sets how background images are repeated.
- `background-origin` : Specify the background positioning area of a background image. This property has no effect if background-attachment is "fixed".
- `background-clip` : Specify how far the background should extend within an element.
- `background-attachment` : Set whether a background image scrolls with the rest of the page, or is fixed.
- `background-blend-mode` : Define the blending mode of each background layer (color and/or image).

