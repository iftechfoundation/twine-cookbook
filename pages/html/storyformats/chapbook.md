# Chapbook HTML

Chapbook uses a variety of HTML elements and attributes to organize its stories.

The following is a snapshot of a Chapbook story for reference and archival purposes.

```html
<form id="cb-validation" action="javascript:void(0)">
  <button id="cb-validation-tester" hidden=""></button>
  <button id="cb-block-enter-key" hidden=""></button>
  <div id="backdrop">
    <div id="page" aria-live="polite">
      <header>
        <div class="left"></div>
        <div class="center"></div>
        <div class="right"></div>
      </header>
      <article style="position: relative;">
        <div class="" style="">
          <p>Double-click this passage to edit it.</p>
        </div>
      </article>
      <ul class="warnings" hidden=""></ul>
      <footer class="has-content">
        <div class="left">
          <p>
            <em>Chapbook HTML</em>
          </p>
        </div>
        <div class="center"></div>
        <div class="right">
          <p>
           <a href="javascript:void(0)" data-cb-restart="true">Restart</a>
          </p>
        </div>
     </footer>
     <div id="spinner">
       <img src="data:image/svg+xml..." width="40" height="40" alt="">
     </div>
   </div>
  </div>
</form>
```
