# "Programmatic Undo": Snowman (v1.3.0)

## Summary

Snowman comes with no user-facing functionality for undoing and re-doing actions. However, though using [jQuery](https://jquery.com/) and a combination of the [*window.story.checkpoint()*](https://twinery.org/wiki/snowman:window-story:checkpoint) and [*window.history.back()*](https://developer.mozilla.org/en-US/docs/Web/API/Window/history) functions, this can be emulated.

<div class="alertbox information"><strong>Note:</strong> Checkpoints will only affect properties of the 's' (state) global variable.</div>

## Twee Code

```
:: StoryTitle
Programmatic Undo in Snowman

:: UserScript[script]
$(window).on('showpassage:after', function (e, data)
{
    window.story.checkpoint(data.passage.name);
});

:: Start
[[Enter the Darkness]]

:: Enter the Darkness
<a href="javascript: window.history.back();">You are not ready! Go back!</a>
```
