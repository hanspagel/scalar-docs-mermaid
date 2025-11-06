# Mermaid

## scalar.config.json

```json
{
  "siteConfig": {
    "bodyScript": "(function(){const init=()=>{const s=document.createElement('script');s.type='module';s.textContent=`import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@11/dist/mermaid.esm.min.mjs';mermaid.initialize({startOnLoad:false});mermaid.run();`;document.head.appendChild(s);};document.readyState==='loading'?document.addEventListener('DOMContentLoaded',init):init();})();"
  }
}
```

## Usage

```html
<pre class="mermaid">
graph TD
    A[Start] --> B{Is it working?}
    B -->|Yes| C[Great!]
    B -->|No| D[Debug]
    D --> B
    C --> E[End]
</pre>
```

## Preview

<pre class="mermaid">
graph TD
    A[Start] --> B{Is it working?}
    B -->|Yes| C[Great!]
    B -->|No| D[Debug]
    D --> B
    C --> E[End]
</pre>
