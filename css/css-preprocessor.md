# CSS Preprocessor

> CSS preprocessors make CSS code more readable and easier to maintain. They have more features than pure CSS such as misin, nesting selector, variables and functions. To use a CSS preprocessor, you must install a CSS compiler on your web server; or upload compiled CSS file to the web server. 

- SCSS and Stylus are the most popular CSS preprocessor.
- Difference between SCSS and SASS
  | SCSS  | SASS |
  | ---| --- |
  | new syntax of Sass | older syntax |
  | use {} and ; | use strict indentation |
  | syntax similar to CSS | syntax similar to Ruby |
  | file extension .scss | file extension .sass |
- Stylus : You can either write it with the indentation rule or with {} and ;. Not only does Stylus support all the features from Less and Sass, it provides features not found anywhere else.
- LESS : Sass and Less have similar features. Sass is based on Ruby whereas Less is based on Javascript. They have a different syntax, for example, Sass uses $ for variables whereas less uses @.
- Syntax Examples :
  1. SASS
      ```scss
      $primary-color: #FF4500
      h1
        color: $primary-color
      ```
  2. SCSS
      ```scss
      $primary-color: #FF4500;
      h1{
        color: $primary-color;
      }
      ```
  3. Stylus 
      ```styl
      /* CSS Style Syntax */
      primary-color: #FF4500;
      h1{
        color: $primary-color;
      }
      /* OR */
      /* Without Curly Braces */
      primary-color: #FF4500;
      h1
        color: $primary-color;
      /* OR */
      /* Without Curly Braces & Semicolons */
      primary-color: #FF4500
      h1
        color: $primary-color
      ```
  4. LESS
      ```less
      @primary-color: #FF4500;
      h1 {
        color: @primary-color;
      }
      ```