# Questions

## How do I remove all Jonah passage titles?*

This CSS sample makes the passage titles invisible:

```css
.passage .title { display: none; }
```

## *How do I remove all Jonah passage titles but the current one?*

This CSS sample makes all passage titles invisible except for the current one:

```css
.passage:not(:last-child) .title { display: none; }
```
