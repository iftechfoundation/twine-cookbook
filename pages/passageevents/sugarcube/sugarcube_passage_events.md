# "Passage Events": SugarCube (v2.18)

## Summary

SugarCube triggers different [events as they happen to passages](http://www.motoslave.net/sugarcube/2/docs/passage-events-task-objects.html). Through using jQuery and its own [JavaScript event handling](http://api.jquery.com/category/events/event-handler-attachment/), code can be added to work with other, existing functionality.

In this example, the "passagestart" and "passagerender" events are shown. In the event progression, the 'passagestart' event occurs before the [PassageHeader](http://www.motoslave.net/sugarcube/2/docs/special-names.html#special-passages-passageheader) prepending its content and the 'passagerender' happens after the [PassageFooter](http://www.motoslave.net/sugarcube/2/docs/special-names.html#special-passages-passagefooter). Through using event handling, content is added before the PassageHeader and after the PassageFooter as an example of when events occur in presenting passages.

## Example

[Download](sugarcube_passage_events_example.html){ target="_top" download="sugarcube_passage_events_example.html"}

## Twee Code

```twee
:: StoryTitle
Passage Events in SugarCube

:: UserScript[script]
/*
    Prepend the content of the passage "New Header" to every passage.

    This demonstrates that the 'passagestart' event comes before
     the PassageHeader prepending.
*/
$(document).on(':passagestart', function (eventObject) {
    var headerContent = Story.get("New Header").processText();
    $(eventObject.content).wiki(headerContent);
});

/*
    Append the content of the passage "New Footer" to every passage.

    This demonstrates that the 'passagerender' event comes after
     the PassageFooter appending.
*/
$(document).on(':passagerender', function (eventObject) {
    var footerContent = Story.get("New Footer").processText();
    $(eventObject.content).wiki(footerContent);
});

:: Start
[[Another passage]]

:: Another passage
[[Back to beginning|Start]]

:: New Header
This is added before the PassageHeader!


:: PassageHeader
This is the PassageHeader.

:: PassageFooter

This is the PassageFooter!

:: New Footer
This is added after the PassageFooter!

```

[Twee Download](sugarcube_passage_events_twee.txt){ target="_top" download="sugarcube_passage_events_twee.txt"}

## See Also

[Headers and Footers](../../headersandfooters/sugarcube/sugarcube_headersandfooters.md)
