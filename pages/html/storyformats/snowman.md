# Snowman HTML

Snowman uses a variety of HTML elements and attributes to organize its stories.

The following are snapshots of HTML element differences between major versions in Snowman.

## Snowman 1.X

```html
<body>
  <div id="main">
    <div class="passage" aria-live="polite">
      <p>Double-click this passage to edit it.</p>
    </div>
  </div>
</body>
```

## Snowman 2.X

```html
<body>
  <tw-story>
    <tw-passage class="passage" aria-live="polite">
      <p>Double-click this passage to edit it.</p>
    </tw-passage>
  </tw-story>
</body>
```
