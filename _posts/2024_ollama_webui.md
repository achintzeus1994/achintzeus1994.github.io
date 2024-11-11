---
title: 'Ollama+Open WebUI Setup'
date: 2021-08-10
permalink: /posts/2021/08/ollama_openwebui/
tags:
  - LLM
---
<!-- MathJax -->
<script type="text/javascript"
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.3/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

<h1 id="introduction">Introduction</h1>
```html
<!-- A simple HTML block with a "copy" button -->
<pre>
<code class="code-to-copy">
let message = "Hello, World!";
console.log(message);
</code>
<button onclick="copyToClipboard(this)" class="copy-button">Copy</button>
</pre>

<script>
function copyToClipboard(button) {
  // Find the closest code block to copy
  const code = button.previousElementSibling;
  navigator.clipboard.writeText(code.textContent)
    .then(() => {
      button.textContent = "Copied!";
      setTimeout(() => (button.textContent = "Copy"), 2000);
    })
    .catch(err => console.error("Failed to copy text: ", err));
}
</script>

<style>
  .copy-button {
    margin-top: 5px;
    cursor: pointer;
    padding: 5px;
  }
</style>
