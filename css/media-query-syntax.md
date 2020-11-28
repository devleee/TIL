# Media Query Syntax

```
media_query_list
 : S* [media_query [ ',' S* media_query ]* ]?
 ;
media_query
 : [ONLY | NOT]? S* media_type S* [ AND S* expression ]*
 | expression [ AND S* expression ]*
 ;
expression
 : '(' S* media_feature S* [ ':' S* expr ]? ')' S*
 ;
```
- media_query_list : Media queries can be used in a form of a list in which each media query is separated with `,`.
  - Example : 
    ```css
    @media screen and (min-width: 768px), screen and (orientation: portrait) {...}
    /* If at least one of the media query is true, it it true*/
    ```
- media_query
  - `only` or `not` keyword can come before the media type. 
  - Media type can be used without expression and vice versa.
  - Expression can be used in a form of a list in which each expression is separated with `and`.
  - White spaces between media type, `and` keyword and expression should be kept.
  - Example : 
    ```css
    @media not screen and (min-width: 768px) {...}
    /* 'not' negates the whole media query, 'screen and (min-width: 768px)' */
    @media screen {...}
    @media (orientation: landscape) {...}
    @media screen and (min-width: 768px) {...}
    @media screen and (min-width: 320px) and (max-width: 767px) {...}
    ```
  - media types : `all`, `screen`, `print`(for documents viewed on a screen in print preview mode), `speech`(for speech synthesizers)
- expression : Expression should be enclosed in brackets().
  - Example :
    ```css
    (color)
    (min-color: 8)
    (orientation: portrait)
    (min-width: 768px)
    ```
  - media features : `aspect-ratio`, `color`, `color-index`, `height`, `width`, `orientation`, `resolution`, [and more](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)