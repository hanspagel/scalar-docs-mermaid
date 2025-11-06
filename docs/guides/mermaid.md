# Mermaid

## Configuration

```json5
// scalar.config.json
{
  "siteConfig": {
    "bodyScript": "(function(){const init=()=>{try{const s=document.createElement('script');s.type='module';s.textContent=`import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@11/dist/mermaid.esm.min.mjs';mermaid.initialize({startOnLoad:false});const runMermaidWithRetry=(attempt=0,maxAttempts=10)=>{const elements=document.querySelectorAll('pre.mermaid,code.mermaid');if(elements.length===0){if(attempt<maxAttempts){setTimeout(()=>runMermaidWithRetry(attempt+1,maxAttempts),300);return;}else{return;}}const checkElementsReady=()=>{let allReady=true;elements.forEach((el,idx)=>{const rect=el.getBoundingClientRect();const hasParent=el.parentElement!==null;const isVisible=rect.width>0&&rect.height>0;if(!hasParent||!isVisible){allReady=false;}});return allReady;};if(!checkElementsReady()){if(attempt<maxAttempts){requestAnimationFrame(()=>{setTimeout(()=>runMermaidWithRetry(attempt+1,maxAttempts),200);});return;}}requestAnimationFrame(()=>{requestAnimationFrame(()=>{try{mermaid.run().then(()=>{}).catch((err)=>{if(attempt<maxAttempts-1){setTimeout(()=>runMermaidWithRetry(attempt+1,maxAttempts),500);}});}catch(e){if(attempt<maxAttempts-1){setTimeout(()=>runMermaidWithRetry(attempt+1,maxAttempts),500);}}});});};setTimeout(()=>{runMermaidWithRetry();},500);`;s.onerror=(e)=>{};s.onload=()=>{};document.head.appendChild(s);}catch(e){}};const readyState=document.readyState;if(readyState==='loading'){document.addEventListener('DOMContentLoaded',()=>{setTimeout(init,100);});}else{setTimeout(init,100);}})();"
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
