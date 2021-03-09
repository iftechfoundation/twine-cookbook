# "CSS Selectors": Snowman (v2.0.2)

## Summary

This example shows how to use [CSS](../../terms/terms_css.md) selectors to style different areas of the page. Snowman 2.0 uses the elements `<tw-story>` and `<tw-passage>` to show a passage. It also changes from an *id* to a *class* named "passage" from previous versions of Snowman.

```html
<body>
  <tw-story>
    <tw-passage class="passage"></tw-passage>
  </tw-story>
</body>
```

## Example

[Download](snowman_cssselectors_example.html){: target="_top" download="snowman_cssselectors_example.html"}

## Twee Code

```twee
:: StoryTitle
CSS Selectors in Snowman

:: UserStylesheet [stylesheet]
body {
    background-color: lightgreen;
}

tw-passage {
    border: 1px solid red;
}

:: Start
The page has a green background; it contains this passage, which has a red border.

[[Second]]

:: Second
This passage also has a red border.

```

[Twee Download](snowman_cssselectors_twee.txt){ target="_top" download="snowman_cssselectors_twee.txt"}

## See Also

See the Snowman [left sidebar](../../sidebar_left/snowman/snowman_sidebar_left.md) for an example of styling passages using the [*id* CSS selector](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors).
