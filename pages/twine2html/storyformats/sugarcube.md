# SugarCube HTML

## SugarCube 1.X HTML

```html
<body>
  <div id="init-screen">
    <p id="init-loading">Initializing. Please wait…<br><progress></progress></p>
  </div>
  <div id="ui-bar">
    <header id="title" role="banner">
      <div id="story-banner"></div>
      <h1 id="story-title">SugarCube HTML</h1>
      <div id="story-subtitle"></div>
      <div id="story-title-separator"></div>
      <p id="story-author"></p>
    </header>
    <nav id="menu" role="navigation">
      <ul id="menu-core">
        <li id="menu-saves"><a>Saves</a></li>
        <li id="menu-restart"><a>Restart</a></li>
      </ul>
    </nav>
  </div>
  <div id="passages" role="main">
    <section id="passage-untitled-passage" class="passage" data-passage="Untitled Passage" style="visibility: visible;">
      <header class="header"></header>
      <div class="body content">Double-click this passage to edit it.</div>
      <footer class="footer"></footer>
    </section>
  </div>
  <div id="ui-overlay" class="ui-close"></div>
  <div id="ui-body"></div>
  <a id="ui-body-close" class="ui-close"></a>
  ...
</body>
```

## SugarCube 2.X HTML

```html
<body>
  <div id="init-screen">
    <div id="init-loading">
      <div>Loading…</div>
    </div>
  </div>
  ...
  <div id="ui-overlay" class="ui-close"></div>
  <div id="ui-dialog" tabindex="0" role="dialog" aria-labelledby="ui-dialog-title">
    <div id="ui-dialog-titlebar">
      <h1 id="ui-dialog-title"></h1>
      <button id="ui-dialog-close" class="ui-close" tabindex="0" aria-label="Close"></button>
    </div>
    <div id="ui-dialog-body"></div>
  </div>
  <div id="ui-bar">
    <div id="ui-bar-tray">
      <button id="ui-bar-toggle" tabindex="0" title="Toggle the UI bar" aria-label="Toggle the UI bar" type="button"></button>
        <div id="ui-bar-history">
          <button id="history-backward" tabindex="0" title="Go backward within the game history" aria-label="Go backward within the game history" disabled="" aria-disabled="true" type="button"></button>
          <button id="history-forward" tabindex="0" title="Go forward within the game history" aria-label="Go forward within the game history" disabled="" aria-disabled="true" type="button"></button>
        </div>
    </div>
    <div id="ui-bar-body">
      <header id="title" role="banner">
        <div id="story-banner"></div>
        <h1 id="story-title">SugarCube HTML</h1>
        <div id="story-subtitle"></div>
        <div id="story-title-separator"></div>
        <p id="story-author"></p>
      </header>
      <nav id="menu" role="navigation">
        <ul id="menu-core">
          <li id="menu-item-saves">
            <a tabindex="0">Saves</a>
          </li>
          <li id="menu-item-restart">
            <a tabindex="0">Restart</a>
          </li>
        </ul>
      </nav>
    </div>
  </div>
  <div id="story" role="main">
    <div id="passages">
      <div id="passage-untitled-passage" data-passage="Untitled Passage" class="passage">Double-click this passage to edit it.</div>
      </div>
    </div>
  </div>
  ...
</body>
```
