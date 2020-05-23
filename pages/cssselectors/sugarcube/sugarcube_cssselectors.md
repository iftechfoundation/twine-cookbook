# "CSS Selectors": SugarCube (v2.18)

## Summary

This example shows how to use [CSS](../../terms/terms_css.md) selectors to style different areas of the page. SugarCube uses nested `<div>`s with ids to structure its significant elements. Most notably the sidebar is a `<div>` with id "ui-bar". However, these elements are often more easily styled by other means, such as selecting the `<body>` element to style the entire page, and the "passage" class to style the current passage.

```html
<body>
  <div id="ui-bar">...</div>
  <div id="story">
    <div id="passages">
      <div id="a-passage-name" class="passage">...</div>
    </div>
  </div>
</body>
```

## Example

[Download](sugarcube_cssselectors_example.html)

## Twee Code

```twee
:: StoryTitle
CSS Selectors in SugarCube

:: UserStylesheet [stylesheet]
body {
    background-color: darkgreen;
}

#ui-bar {
    border: 2px solid blue;
}

.passage {
    border: 1px solid red;
}

:: Start
The page has a green background; it contains this passage (red border) and the sidebar (blue border).
[[Second]]

:: Second
This passage also has a red border.
```

[Twee Download](sugarcube_cssselectors_twee.txt)

## See Also

See the [SugarCube images](../../images/sugarcube/sugarcube_images.md) for an example of using a single [*class* CSS selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors) to style a different element. See [styling passages by tag](../../passagetags/sugarcube/sugarcube_passagetags.md) for an example of using two classes to style a single element.
