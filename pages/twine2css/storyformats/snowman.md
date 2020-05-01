# Snowman CSS

The HTML structure of Snowman stories differs across its two main branches. For Snowman 1.X, passages are part of a `<div id="main">`. In Snowman 2, the main element is `<tw-passage>`.

Both branches use the `class` "passage". This can be used to define or overwrite existing CSS rules provided by the story format.

## Snowman 1.X HTML

```html
<body>
  <div id="main">
    <div class="passage" aria-live="polite">
      <p>Double-click this passage to edit it.</p>
    </div>
  </div>
</body>
```

## Snowman 2.X HTML

```html
<body>
  <tw-story>
    <tw-passage class="passage" aria-live="polite">
      <p>Double-click this passage to edit it.</p>
    </tw-passage>
  </tw-story>
</body>
```

## Snowman Links

Snowman uses the anchor element, `<a>`, for all links. However, as links are re-generated at the start of each passage, the pseudo-class `visited` will not have an effect. `hover`, however, will.

```css
a {
 color: blue;
}

a:hover {
 color: green;
}
```
