# Using `target="_blank"` attribute in an `<a>` tag

>`<a>` tag can have the `target` attribute to specify where to open the linked document. The default value is `_self` (which means opening the link in the current tab). `target="_blank"` can be used to open the link in a new tab but there are some things need to be considered.

### 1. Do you really need to use `target="_blank"`?
- `target="_self"` is the default for reason. Most browsers allow users to choose where to open the link, so let the users handle it. Use it only when you want to leave the current page as it is, for example:
  - The user is working on something on the page and it will be lost if the current page changes.
  - There is user-initiated media (audio, video, ...) playing on the page.
  - There is a specific technical/business requirement to do so.

### 2. If you have to use `target="_blank"`, use `rel="noreferrer noopener"` with it to avoid security issues.
```html
<a href="https://somelink.com" target="_blank" rel="noreferrer noopener">
```
- The newly opened tab gains partial access to the linking page via `window.opener` object so it can then change the `window.opener.location` to lead users to a phishing website. 
- `rel="noreferrer"` hides referrer information and prevents the newly opened site from manipulating the window.opener object. 
- `rel="noopener"` prevents providing window.opener property to the newly opened site by not setting it.
- It is recommended to use both since noopener is not supported in some browsers.
- But the best approach is to avoid using `target="_blank"`

---
Reference: <br>
[When should you use target blank](https://stackoverflow.com/questions/946248/when-should-you-use-target-blank-on-your-links)<br>
[Target="_blank" - the most underestimated vulnerability ever](https://www.jitbit.com/alexblog/256-targetblank---the-most-underestimated-vulnerability-ever/)<br>
[Reverse Tabnabbing](https://techblog.topdesk.com/security/developers-need-know-reverse-tabnabbing/)