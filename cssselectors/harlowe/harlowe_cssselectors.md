# "CSS Selectors": Harlowe (v2.0)

<div class="alertbox warning"><strong>Note:</strong> The following example is designed for use in Harlowe 2.x and later</div>

## Summary

This example shows how to use [CSS](../../terms/terms_css.md) selectors to style different areas of the page.  In Harlowe, custom HTML elements are used for layout:  the `<tw-story>` element contains the page as well as a an element containing the currently shown passage, `<tw-passage>`, and an element containing the sidebar, `<tw-sidebar>`.

```
<tw-story>
	<tw-passage>
		<tw-sidebar>...</tw-sidebar>
		...
	</tw-passage>
</tw-story>
```

## Live Example

<section>
<iframe src="harlowe_cssselectors_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_cssselectors_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
CSS Selectors in Harlowe

:: UserStylesheet [stylesheet]
tw-story {
    border: 5px solid lightgreen;
}

tw-sidebar {
    border: 2px solid blue;
}

tw-passage {
    border: 1px solid red;
}

:: Start
The page has a green border; it contains this passage (red border) and the sidebar (blue border).
[[Second]]

:: Second
This passage also has a red border.

```

Download: <a href="harlowe_cssselectors_twee.txt" target="_blank">Twee Code</a>

## See Also

See the [left sidebar recipe](../../sidebar_left/harlowe_2/harlowe_sidebar_left.md) for another example of stylying custom elements like `<tw-sidebar>`. Harlowe also supports [styling passages by tag](../../passagetags/harlowe/harlowe_passagetags.md) using its custom 'tags' attribute.
