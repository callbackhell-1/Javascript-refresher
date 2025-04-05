## Using `<script>` Tag

### 📍 In the `<head>`

- The browser **downloads the script first**, then **executes it**, and **only after that** starts downloading the HTML.
- ❌ _Not ideal_ — slows down page rendering.

### 📍 At the end of the `<body>`

- The browser **downloads and builds the HTML (DOM)** first, then **downloads and runs the script**.
- ✅ _Better_, but can be a bit **slower for large scripts**.

### ⚡ With `async`

```html
<script async src="script.js"></script>
```

- The browser downloads HTML and script at the same time.
- As soon as the script is downloaded, it runs immediately, even if the HTML is still loading.
- ✅ Great for independent scripts like analytics that don’t depend on the DOM or other scripts.
- ⚠️ Scripts may run out of order.

### ⏳ With `defer` :

`<script defer src="script.js"></script>`

- The browser downloads HTML and script in parallel.
- Script waits until the HTML is fully loaded and DOM is built, then runs.
- ✅ Best for scripts that depend on the DOM or need to run in order.
- ✅ Scripts with defer run in order.
