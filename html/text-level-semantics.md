# Text-level Semantics
>Each formatting elements has different meaning even though some of them have outcomes look the same.

### `<i>`
- Typically displayed in *italic*.
- Defines a part of text in an alternate voice or mood.
- Or indicates a technical term, a phrase from another language, a thought, a ship name, etc.
- Example :
  ```html
  <p>There is a certain <i lang="fr">je ne sais quoi</i> in the air.</p>
  ```
- Use the `<i>` element only when there is not a more appropriate semantic element, such as: `<em>`, `<cite>`, `<dfn>`.

### `<b>`
- Make text **bold** (without marking it as important).
- Can be used to mark key words in a document abstract, product names in a review, actionable words in interactive text-driven software, or an article lede.
- Example : 
  ```html
  <article>
    <h2>Kittens 'adopted' by pet rabbit</h2>
    <p><b class="lede">Six abandoned kittens have found an unexpected new mother figure — a pet rabbit.</b></p>
    <p>Veterinary nurse Melanie Humble took the three-week-old kittens to her Aberdeen home.</p>
    [...]
  </article>
  ```
- Use the `<i>` element only when there is not a more appropriate semantic element, such as: `<h1>` ~ `<h6>`, `<strong>`, `<mark>`.

### `<u>`
- Typically displayed with an <u>underline</u>.
- Represents some text that is unarticulated and styled differently from normal text, such as misspelled words.
- Example : 
  ```html
  <p>This is some <u>mispeled</u> text.</p>
  ```
- Avoid using the `<u>` element where it could be confused for a hyperlink.
- In most cases, another element is likely to be more appropriate. Use it only when it can't be replaced with `<em>`, `<mark>`, `<cite>`, `<i>`, `<ruby>`.

### `<s>`
- Displayed with a ~~line through~~ it.
- Specifies text that is no longer correct, accurate or relevant.
- Example : 
  ```html
  <p>Sale</p>
  <p><s>Price: $19.50</s></p>
  <p><strong>Now selling for $12.99</strong></p>
  ```
- Not appropriate to use `<s>` when indicating deleted text. Use `<del>` instead.