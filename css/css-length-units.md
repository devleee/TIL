# CSS Length Units

### `px`
- Absolute length unit
- 1px = 1/96th of 1in

### `em`
- Relative length unit
- In the case of **typographical properties** (font-size) : relative to the font size of the **parent**
- In the case of **other** properties : relative to the font size of the element **itself**
- When to use `em`?
  - For sizing that should scale depending on the font size of an element, for example for the paddings and margins of a `button`.

### `rem`
- Relative length unit
- Relative to font-size of the **root element** (default: 16px)
- When to use `rem`?
  - To enable the font sizes to scale depending on user's browser font size settings (But most modern browsers zoom all elements equally anyway, so using px is not a problem).
  - If you have to change the font sizes in different screen sizes, `rem` can be useful as you don't have to change the font sizes of all the elements. Instead, you only need to change the font-size of the root element
- If you want to support the older versions of IE, you have to use pixel fallback.