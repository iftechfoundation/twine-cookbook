# "Passage Transitions": Snowman (v1.3)

## Summary

In Snowman, the "showpassage" event is triggered once a passage is loaded. By listening for this event, [jQuery effects](https://api.jquery.com/category/effects/) can be applied to the passage element to produce a transition.

## Example

[Download](snowman_passagetransitions_example.html)

## Twee Code

```twee
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

[Twee Download](snowman_passagetransitions_twee.txt)
