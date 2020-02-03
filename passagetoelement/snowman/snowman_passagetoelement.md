# "Render Passage to Element": Snowman (v2.0.0)

## Summary

In Snowman, the function **[renderToSelector()](https://videlais.github.io/snowman/2/utility/renderToSelector.html)** renders the contents of a passage into an element based on its [jQuery selector](https://api.jquery.com/category/selectors/).

The event ["sm.passage.shown"](https://videlais.github.io/snowman/2/events/passage_events.html) is used in this example to guarantee that the passage has been rendered before acting. Calling the function **renderToSelector()** inside the [jQuery event listener](https://api.jquery.com/on/) then renders another passage into an existing element.

## Live Example

<section>
<iframe src="snowman_passagetoelement_example.html" height=400 width=90%></iframe>

Download: <a href="snowman_passagetoelement_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Snowman: Render to Element

:: Start
<div id="hudID"></div>
<script>
$(document).one('sm.passage.shown', function (ev) {
	// Render the passage named HUD into the element with id of "hudID"
		renderToSelector("#hudID", "HUD");
	});
</script>

:: HUD
<h1>This is the HUD!</h1>

```

Download: <a href="snowman_passagetoelement_twee.txt" target="_blank">Twee Code</a>
