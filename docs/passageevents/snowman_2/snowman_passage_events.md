# "Passage Events": Snowman (v2.0.0)

## Summary

Snowman triggers different events [as they happen to passages](https://videlais.github.io/snowman/2/events/passage_events.html).

In this example, a header and footer is created by listening for the 'sm.passage.shown' event with a [jQuery event handle](http://api.jquery.com/category/events/event-handler-attachment/) and then prepending the content of the passage "Header" and appending the content of the passage "Footer" to the current passage after it has been initially rendered.

## Live Example

<section>
<iframe src="snowman_passage_events_example.html" height=400 width=90%></iframe>

Download: <a href="snowman_passage_events_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```twee
:: StoryTitle
Snowman 2: Passage Events

:: UserScript[script]
/*
    Prepend the content of the passage "Header" to every passage.
		Append the content of the passage "Footer" to every passage.
*/
$(window).on('sm.passage.shown', function (eventObject, passageObject) {
		var headerContent = window.story.render("Header");
		var currentContent = passageObject.passage.render();
		var footerContent = window.story.render("Footer");

		$('tw-passage').html(headerContent + currentContent + footerContent);
});

:: Start
<p>[[Another Passage]]</p>

:: Another Passage
[[Back to beginning->Start]]

:: Header
This is the header!

:: Footer
This is the footer!

```

Download: <a href="snowman_passage_events_twee.txt" target="_blank">Twee Code</a>

## See Also

[Headers and Footers](../../headersandfooters/snowman/snowman_headersandfooters.md)
