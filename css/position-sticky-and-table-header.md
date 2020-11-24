# `position: sticky` And Table Header

> Sticky table header can be useful if the content of the table is longer than the screen height.

- `position: sticky` doesn't work with `<thead>` or`<tr>`. So if you want to make a sticky table header, you have to apply `position: sticky` to `<th>`.
- `top` property should have a value to make it work.
 ```css
 th {
   position: sticky;
   top: 0;
 }
 ```
- [Example](https://codepen.io/devleee/pen/mdrbmyG)