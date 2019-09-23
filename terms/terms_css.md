# CSS

[Cascading Style Sheets](https://en.wikipedia.org/wiki/Cascading_Style_Sheets) (CSS) is a style sheet language for describing the presentation of HTML elements, *i.e.*, the  colors, fonts, spacing, and general layout of a web page.  "Cascading" means that multiple style sheets may be present, and that conflicting style directives within or between stylesheets are prioritized in a specific, predictable way.

CSS styles are associated with [HTML elements](https://en.wikipedia.org/wiki/HTML_element) using the element's (tag)name, id, classes, and/or other, possibly custom, [attributes](https://en.wikipedia.org/wiki/HTML_attribute).   Each built-in story format in Twine 2 uses different, sometimes custom, HTML elements to organize the story, and then applies its own CSS stylesheet to those elements.

## Story Stylesheet

When using Twine, additional CSS styles can be added through the Story Stylesheet screen.  This CSS is inserted into the final story and provides an opportunity to override the color and formatting choices expressed in the story format's own stylesheet.  (When using Twee, styles can be added using one or more passages tagged `stylesheet`.)

Considering the complex nature of CSS cascading, it is always highly recommended to use a story format's own macros where possible to change the presentation or layout of a story.

Common areas involved in story format styling include the full page or window, a sidebar (if present), and the current [passage](../terms/terms_passages.md) as a sub-area of the page.  Often there is also a mechanism to style passages according to its tags (as assigned in Twine 2).

### Harlowe

Harlowe uses the custom `<tw-story>` element to style the page.  It also contains an element for the currently shown passage, `<tw-passage>`.  The sidebar is inside (a child of) each passage and is contained in the element `<tw-sidebar>`.  

```
<tw-story tags="grey">
	<tw-passage tags="grey">
		<tw-sidebar>...</tw-sidebar>
		...
	</tw-passage>
</tw-story>
```

See the [left sidebar recipe](../sidebar_left/harlowe_2/harlowe_sidebar_left.md) for an example of stylying custom elements like `<tw-sidebar>`.  Harlowe also supports [styling passages by tag](../passagetags/harlowe/harlowe_passagetags.md) using its custom `tags` attribute.

### SugarCube

SugarCube uses nested `<div>`s with ids to structure its significant elements.  Most notably the sidebar is a `<div>` with id `ui-bar`.  However, its elements are often more easily styled without ids: in many cases the `<body>` element can be used to style the entire page, the `passage` class for the current passage, and tag classes to style elements based on the current passage's tag.

```
<body>
	<div id="ui-bar">...</div>
	<div id="story">
		<div id="passages">
			<div id="a-passage-name" class="passage">...</div>
		</div>
	</div>
</body>
```

See the [SugarCube images recipe](../images/sugarcube/sugarcube_images.md) for an example of using a single [*class* CSS selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors) to style an element.   See [styling passages by tag](../passagetags/sugarcube/sugarcube_passagetags.md) for an example of using two classes to style a single element.

#### Bleached

[Bleached](https://www.motoslave.net/sugarcube/2/#downloads) is an alternate, light-colored stylesheet for SugarCube, and a good example of how to change SugarCube's default colors using CSS.

### Snowman

Snowman uses a simple HTML structure of a `<div>` with id `passage` directly below (inside) the `<body>` tag.  See the Snowman [left sidebar recipe](../sidebar_left/snowman/snowman_sidebar_left.md) for an example of styling passages using the [*id* CSS selector](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors).

```
<body>
	<div id="passage">...</div>
</body>
```



