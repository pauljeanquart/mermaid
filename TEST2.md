```mermaid
flowchart LR
    A:::someclass --> B
    classDef someclass fill:#f96;
```

# Ignore scripts
<script src="https://cdnjs.cloudflare.com/ajax/libs/mermaid/9.2.2/mermaid.min.js" integrity="sha512-IX+bU+wShHqfqaMHLMrtwi4nK6W/Z+QdZoL4kPNtRxI2wCLyHPMAdl3a43Fv1Foqv4AP+aiW6hg1dcrTt3xc+Q==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
<script>
  // select <pre class="mermaid"> _and_ <pre><code class="language-mermaid">
document.querySelectorAll("pre.mermaid, pre>code.language-mermaid").forEach($el => {
  // if the second selector got a hit, reference the parent <pre>
  if ($el.tagName === "CODE")
    $el = $el.parentElement
  // put the Mermaid contents in the expected <div class="mermaid">
  // plus keep the original contents in a nice <details>
  $el.outerHTML = `
    <div class="mermaid">${$el.textContent}</div>
    <details>
      <summary>Diagram source</summary>
      <pre>${$el.textContent}</pre>
    </details>
  `
})

// initialize Mermaid to [1] log errors, [2] have loose security for first-party
// authored diagrams, and [3] respect a preferred dark color scheme
mermaid.initialize({
  logLevel: "error", // [1]
  securityLevel: "loose", // [2]
  theme: (window.matchMedia && window.matchMedia("(prefers-color-scheme: dark)").matches) ?
    "dark" :
    "default" // [3]
})
</script>

