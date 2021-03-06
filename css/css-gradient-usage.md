# CSS Gradient Usage

> CSS gradient can be used to create various graphic elements such as gradient backgrounds, gradient texts, patterns and even icons and graphs.

### Basic Syntax
  ```css
  /* 1. Linear Gradient */
  linear-gradient(
    [ <angle> | to <side-or-corner> ]? ,
    <color-stop-list>
  )

  repeating-linear-gradient(
    [ <angle> | to <side-or-corner> ]? ,
    <color-stop-list>
  )

  <side-or-corner> = [to left | to right] || [to top | to bottom]
  
  /* 2. Radila Gradient */
  radial-gradient(
    [ <ending-shape> || <size> ]? [ at <position> ]? ,
    <color-stop-list>
  )

  repeating-radial-gradient(
    [ <ending-shape> || <size> ]? [ at <position> ]? ,
    <color-stop-list>
  )

  /*By default shape is ellipse, size is farthest-corner, and position is center. */

  /* 3. Conic Gradient */
  conic-gradient(
    [ from <angle> ]? [ at <position> ]?,
    <angular-color-stop-list>
  )
  ```

### Usage
1. Gradient Background
    - [CSS gradient generator](https://cssgradient.io/)

2. Gradient Text
    - [How to add a gradient overlay to text with CSS](https://fossheim.io/writing/posts/css-text-gradient/)

3. Pattern
    - [Patterns with CSS Gradients](https://cssgradient.io/blog/gradient-patterns/)
    - [CSS3 Patterns Gallery](https://projects.verou.me/css3patterns/)
    - [CSS Pattern Gradients - by Felix Rilling](https://codepen.io/FelixRilling/pen/LEzPrr)

4. Graph
    - [gradient를 활용하여 그래프 만들기 - WIT블로그](https://wit.nts-corp.com/2018/12/11/5443)
    - [How to Create CSS Conic Gradients for Pie Charts and More](https://www.sitepoint.com/create-css-conic-gradients-pie-charts/)
    - [Simple pie charts with fallback, today](https://lea.verou.me/2020/11/simple-pie-charts-with-fallback-today/)

5. Icon
    - [Gradient Shapes](https://yuanchuan.dev/gradient-shapes/)

### Practice
- [Basic Gradient](https://codepen.io/devleee/pen/GRjpgPq)

