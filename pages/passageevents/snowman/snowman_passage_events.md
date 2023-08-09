# "Passage Events": Snowman (v1.4.0)

## Summary

Snowman triggers different events [as they happen to passages](https://videlais.github.io/snowman/#/1/events/passage_events).

In this example, a header and footer is created by listening for the 'shown.sm.passage' event with a [jQuery event handle](http://api.jquery.com/category/events/event-handler-attachment/) and then prepending the content of the passage "Header" and appending the content of the passage "Footer" to the current passage after it has been initially rendered.

## Example

[Download](snowman_passage_events_example.html){: target="_top" download="snowman_passage_events_example.html"}

## Twee Code

```twee
:: StoryTitle
Snowman: Passage Events

:: UserScript[script]
/*
    Prepend the content of the passage "Header" to every passage.
    Append the content of the passage "Footer" to every passage.
*/
$(window).on('shown.sm.passage', function (eventObject, passageObject) {
    var headerContent = window.story.render("Header");
    var currentContent = passageObject.passage.render();
    var footerContent = window.story.render("Footer");

    $('#main').html(headerContent + currentContent + footerContent);
});

:: Start
[[Another Passage]]

:: Another Passage
[[Back to Beginning|Start]]

:: Header
This is the header!

:: Footer
This is the footer!

```

[Twee Download](snowman_passage_events_twee.txt){ target="_top" download="snowman_passage_events_twee.txt"}

## See Also

[Headers and Footers](../../headersandfooters/snowman/snowman_headersandfooters.md)
