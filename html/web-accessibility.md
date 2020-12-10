# Web accessibility

> Web Content Accessibility Guidelines (WCAG) is developed to make **web content** (1. text, images, and sounds 2. code or markup that defines structure, presentation, etc.) more accessible to people with disabilities.

## Text Alternatives
- Provide text alternatives for any non-text content to make it accessible through screen readers.
    - Describe the appearance, text or function of an image on a page.
    - Describe the image, and be specific.
    - Keep it fewer than 125 characters.
    - Don't start with "Picture of..." or "Image of..." 
      ```html
      <!-- (1) Describing image -->
      <img src="Starlings in silhouette as the sun sets in Stoney Middleton">

      <!-- (2) Text banner -->
      <img src="side-banner.png" alt="Sign up now and start your free trial!">
      <!-- OR if the text is too long provide hidden text-->
      <img src="side-banner.png" alt="">
      <p style="visibility: hidden">
        Sign up now and start learning everything you want from ...
      </p>

      <!-- (3) Image button -->
      <img src="btn_next.png" alt="Go to the next page">
      <!-- OR -->
      <a href="#" style="background-image:url('./img/icon_next.png')">Go to the next page</a>

      <!-- (4) QR code -->
      <a href="http://www.naver.com">
        <img src="qr-code.png" alt="Link to Naver">
      </a> 
      ```
    - If it is a decorative image that doesn't need description, use empty `alt` attribute. If you don't write `alt` at all, the screen reader will read the file name. 
      ```html
      <img src="decorative-line.png" alt="">
      ```

