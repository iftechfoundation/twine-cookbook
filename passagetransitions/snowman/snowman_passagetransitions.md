# "Passage Transitions": Snowman (v1.3)

## Summary

In Snowman, the `showpassage` event is triggered once a passage is loaded. By listening for this event, [jQuery effects](https://api.jquery.com/category/effects/) can be applied to the passage element to produce a transition.

## Live Example

<section>
<iframe src="snowman_passagetransitions_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_passagetransitions_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Snowman: Passage Transitions

:: UserScript[script]
$(document).on('showpassage', function(event, passage) {

	$("#passage").hide(0).fadeIn(2000);

});

:: Start
[[Another Passage]]

:: Another Passage
[[A Third Passage]]

:: A Third Passage
Double-click this passage to edit it.

```

Download: <a href="snowman_passagetransitions_twee.txt" target="_blank">Twee Code</a>
