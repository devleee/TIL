# `content-visibility`
> Enables the browser to skip rendering an element until it is needed to make the initial load faster for long pages.
- It is not widely supported yet. Supported only in recent Chrome, Edge, and Opera.
- It is different from **lazy loading**. Lazy loading does not request the data until it is needed while with `content-visibility` the browser still requests all the data, it just won't render it.

### Values
- `content-visibility: visible` : No effect. The element's contents are rendered as usual.
- `content-visibility: hidden` : Skips rendering the element's contents. The contents won't be accessible.
  - Difference between `content-visibility: hidden` and `display: none` : The contents of `content-visibility: hidden` will preserve rendering state. So when the content is shown again, it will render quicker than `display: none`.
  - Difference between `content-visibility: hidden` and `visibility:hidden` : The contents of `visibility: hidden` will be rendered on page load.
- `content-visibility: auto` : Render the element's contents just before the element scrolls into view.
Unlike hidden, the skipped contents still be available to user-agent features such as in-page anchor navigation, text search and be focusable and selectable.
  ```css
  .my-page-section {
    content-visibility: auto;
    contain-intrinsic-size: 0 1000px;
    /* when the element is still not in the view, it will size as if it has a child of 0x 1000px*/
  }
  ```

