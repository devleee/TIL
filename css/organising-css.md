# Organising CSS

> There are 3 most used methodologies: OOCSS, BEM and SMACSS. All of these are used to increase code reusability, to make the code scalable and efficient.

### OOCSS
- **Object Oriented CSS**
- A methodology designed by Nicole Sullivan
- Seperate structure and skin : Don't repeat the same styles in CSS. Extract common styles and make them reusable
- Seperate container and content : Styles shouldn't be dependent on certain container, it should be able to be reused anywhere in the document.


### BEM
- **Block, Element and Modifier**
- A concrete application of the OOCSS principles, created by Yandex.
- Block : A logically and functionally independent page component. Blocks being independent allows for their re-use.
- Element : A constituent part of a block that can't be used outside of it.
- Modifier : (Optional) A BEM entity that defines the appearance and behavior of a block or an element.
- BEM only uses class selectors, does not use HTML tags or IDs as selectors.

  ```css
  /* Block*/
  .btn {}

  /* Element */ 
  .btn__submit {}

  /* Modifier*/
  .btn--big {} 
  ```

### SMACSS
- **Scalable & Modular Architecture for CSS**
- A methodology designed by Jonathan Snook
- Organise CSS rules in 5 different categories: base, layout, module, state and theme.
- Base : Default styles. Includes tags selectors and also included reset.css.
  ```css
  body, form {
    margin: 0;
    padding: 0;
  }
  ```
- Layout : Divides css in sections. ID for single-use section, class (with “l-” or “layout-” prefix) for multiple-use section.
  ```css
  #header, #article, #footer {
    width: 960px;
    margin: auto;
  }

  .l-fixed #article {
    width: 600px;
  }
  ```
- Module : It consist of reusable blocks which are smaller than layouts. Not recommended to use ID, use class.
- State : Styles of elements status (active, inactive, disable, hidden, expanded, ...)
  ```css
  .tab {
    background-color: purple;
    color: white;
  }

  .is-tab-active {
    background-color: white;
    color: black;
  }
  ```
- Theme : (Optional) Allows the more visual aspects of the project
