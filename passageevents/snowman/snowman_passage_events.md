# "Passage Events": Snowman (v1.3.0)

## Summary

Snowman triggers different events [as they happen to passages](https://twinery.org/wiki/snowman:passage-events). The 'hidepassage' event occurs as a passage is about to be replaced, the 'showpassage' event occurs before the passage is rendered, and the 'showpassage:after' event occurs after everything has been processed.

In this example, a header and footer is created by listening for the 'showpassage:after' event with a [jQuery event handle](http://api.jquery.com/category/events/event-handler-attachment/) and then prepending the content of the passage "Header" and appending the content of the passage "Footer" to the current passage after it has been initially rendered.

## Twee Code

```
:: StoryTitle
Passage Events in Snowman

:: UserScript[script]
/*
    Prepend the content of the passage "Header" to every passage.
		Append the content of the passage "Footer" to every passage.
*/
$(document).on('showpassage:after', function (eventObject, passage) {
		var headerContent = window.story.render("Header");
		var currentContent = $('#passage').html();
		var footerContent = window.story.render("Footer");

		$('#passage').html(headerContent + currentContent + footerContent);  
});


:: Start
[[Another Passage]]

:: Header
This is the header!

:: Footer
This is the footer!

:: Another Passage
[[Back to Beginning|Start]]

```

## See Also

[Headers and Footers](../../headersandfooters/snowman/snowman_headersandfooters.md)
