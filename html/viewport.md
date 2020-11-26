# Viewport

> Viewport (of the browser) : The area of the window in which web content can be seen. 

- Why do you need **viewport meta tag**? <br>
  Often the viewport is not the same size as the rendered page. Webkit-based browsers (Safari for iPhone, Chrome for Android) have default viewport width of 980px. This makes media queries for the narrow screens useless. To solve this problem viewport meta tag should be set in the HTML.
  ```html
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <!-- This is required to use media queries in narrow screens (mobile and tablet) -->
  ```
  - `width=device-width` : Sets the width of the page to follow the screen-width of the device.
  - `initial-scale=1` : Sets the initial zoom level when the page is first loaded.
  - Avoid setting `user-scalable=no`. It prevents users from resizing documents. Disabling zooming can cause problems for users with low vision (it makes the web site less accessible).
  - You can set `minimum-scale` and `maximum-scale`. Default values are `0.25` and `1.6` each. Avoid setting them to `1.0` which prevent users from zooming the page.