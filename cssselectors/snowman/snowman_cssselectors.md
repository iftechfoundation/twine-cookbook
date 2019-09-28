# "CSS Selectors": Snowman (v1.3.0)

## Summary

This example shows how to use [CSS](../../terms/terms_css.md) selectors to style different areas of the page.  Snowman uses a simple HTML structure of a `<div>` with id `passage` directly below (inside) the `<body>` tag.

```
<body>
	<div id="passage">...</div>
</body>
```

## Live Example

<section>
<iframe src="snowman_cssselectors_example.html" height=400 width=90%></iframe>

Download: <a href="snowman_cssselectors_example.html" target="_blank">Live Example</a>
</section>

## Twee Code


```
:: StoryTitle
CSS Selectors in Snowman

:: UserStylesheet [stylesheet]
body {
    background-color: lightgreen;
}

#passage {
    border: 1px solid red;
}

:: Start
The page has a green background; it contains this passage, which has a red border.

[[Second]]

:: Second
This passage also has a red border.

```

Download: <a href="snowman_cssselectors_twee.txt" target="_blank">Twee Code</a>

## See Also

See the Snowman [left sidebar recipe](../../sidebar_left/snowman/snowman_sidebar_left.md) for an example of styling passages using the [*id* CSS selector](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors).
