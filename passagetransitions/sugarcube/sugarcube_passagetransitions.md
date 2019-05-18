# "Passage Transitions": SugarCube (v2.18)

## Summary

SugarCube provides multiple ways to address passage transitions. To work with the existing functionality, the [*Config.passages.transitionOut*](http://www.motoslave.net/sugarcube/2/docs/#config-api-property-passages-transitionout) variable can be set to change the property (height, width, opacity, etc) of the passage element or the amount of time to retain the outgoing passage before removing it with the default transition effect.

Through using [jQuery event listeners](https://api.jquery.com/category/events/), different functionality can be triggered as part of normal passage events such as rendering or displaying content. Acting on the *:passagerender* event, for example, could be used to apply a [jQuery effect](https://api.jquery.com/category/effects/) on the passage element after it has been loaded and rendered.

## Twee Code

```
:: StoryTitle
SugarCube: Passage Transitions

:: UserScript[script]
// Fade in content using jQuery Effects
// Hide and then fade in the content over 2000ms (2s)
$(document).on(':passagerender', function (event) {
	$(".passage").hide(0).fadeIn(2000);
});

:: Start
[[Another passage]]

:: A third passage
No more content!

:: Another passage
[[A third passage]]

```
