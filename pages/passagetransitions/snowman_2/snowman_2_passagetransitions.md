# "Passage Transitions": Snowman (v2.0)

## Summary

In Snowman 2.X, the `sm.passage.showing` event is triggered [once a passage is loaded](https://videlais.github.io/snowman/#/2/events/passage_events). By listening for this event, [jQuery effects](https://api.jquery.com/category/effects/) can be applied to the passage element to produce a transition. (In Snowman 2.X, the passage is the `tw-passage` [element](https://videlais.github.io/snowman/#/2/htmlandcss/elements).)

## Example

[Download](snowman_2_passagetransitions_example.html){: target="_top" download="snowman_2_passagetransitions_example.html"}

## Twee Code

```twee
:: StoryTitle
Snowman 2: Passage Transitions

:: UserScript[script]
$(document).on('sm.passage.showing', function(event, passage) {

  $("tw-passage").hide(0).fadeIn(2000);

});

:: Start
[[Another Passage]]

:: Another Passage
[[A Third Passage]]

:: A Third Passage
Double-click this passage to edit it.

```

[Twee Download](snowman_2_passagetransitions_twee.txt){ target="_top" download="snowman_2_passagetransitions_twee.txt"}
