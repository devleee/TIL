# Cascading

> Cascading algorithm determines which CSS rules apply when there are more than one rule.

### Cascading order
1. Importance : Rules with `!important` keyword overrule all the others
2. Source :
  - If there is `!important` : user agent (browser) > user > author
  - If there is no `!important` : author > user > user agent (browser)
3. [Specificity](https://github.com/devleee/TIL/blob/master/css/specificity.md)
4. If there is more than one rule with equal importance/source/specificity, the one that comes last in the CSS is the one that will be used.

Example : 
  What colour is *item 1* be?
  ```html
    <div id="foo">
      <h1 class="bar">title</h1>
      <ul class="baz" style="color: blue;">  
        <li class="list_item item_1">item 1</li>
        <li class="list_item item_2">item 2</li>
      </ul>
    </div>
  ```
  ```css
    #foo { color: red !important; } /* inherited property -> does not have specificity */
    div > ul > li.item_1 { color: green; } /* 0,0,1,3 */
    .baz > .list_item { color: purple; } /* 0,0,2,0 */
    .list_item.item_1 { color: yellow; } /* 0,0,2,0 -> specificity is the same as the second one but this one came later */
  ```
  It is yellow.
