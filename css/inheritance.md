# Inheritance

>When no value is specified for a property on an element, if the property is **inherited property** the value is set to the computed value of the parent by default and if the property is **non-inherited property** the value is set to initial value of the property by default.

### Inherited properties
- The default value is the **computed value** of the parent.
- **Computed value** : The value that actually applies to the element after the CSS is fully interpreted.

### Non-inherited properties
- The default value is the initial value of the property.
- Box modeil properties are non-inherited properties. (ex: margin, padding, background, border)
- By using `inherit` keyword, the author can specify inheritance. If you want to apply `inherit` to all properties, use `all` property.
  ```css
  .foo {
    all: inherit;
  }
  ```

### CSS values for controlling inheritance
- `inherit` : Take the computed value of the property from its parent element.
- `initial` : Take the the initial/default value of the property.
- `unset` : Take the computed value of the property from its parent element if the property naturally inherits from its parent, take its initial value if not.
- `revert` :  Resets the property to its inherited value if it inherits from its parent or to the default value of the user agent(browser)'s stylesheet.

### Inheritance and Specificity
- Inherited properties do not have any specificity
  ```html
  <h1 id="bar">
    This should be blue and 
    <em>this should be red, not blue</em>
  </h1>
  ```
  ```css
  * { color: red; }
  #bar { color: blue; }
  /* the universal selector has specificity of 0,0,0,0
  even so the properties of the universal selector is more important then inherited properties*/
  ```
