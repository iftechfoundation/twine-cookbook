# "CSS Selectors": Harlowe (v2.0)

!!! Warning
    The following example is designed for use in Harlowe 2.x and later

## Summary

This example shows how to use [CSS](../../terms/terms_css.md) selectors to style different areas of the page. In Harlowe, custom HTML elements are used for layout:  the `<tw-story>` element contains the page as well as a an element containing the currently shown passage, `<tw-passage>`, and an element containing the sidebar, `<tw-sidebar>`.

```twee
<tw-story>
  <tw-passage>
    <tw-sidebar>...</tw-sidebar>
    ...
  </tw-passage>
</tw-story>
```

## Example

[Download](harlowe_cssselectors_example.html)

## Twee Code

```twee
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

[Twee Download](harlowe_cssselectors_twee.txt)

## See Also

See the [left sidebar](../../sidebar_left/harlowe_2/harlowe_sidebar_left.md) for another example of styling custom elements like `<tw-sidebar>`. Harlowe also supports [styling passages by tag](../../passagetags/harlowe/harlowe_passagetags.md) using its custom 'tags' attribute.
