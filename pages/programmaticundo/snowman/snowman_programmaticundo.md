# "Programmatic Undo": Snowman (v1.3.0)

!!! Information
    Checkpoints will only affect properties of the **s** (state) global variable in Snowman.

## Summary

Snowman comes with no user-facing functionality for undoing and re-doing actions. However, though using [jQuery](https://jquery.com/) and a combination of the **[window.story.checkpoint()](https://videlais.github.io/snowman/#/1/window_story/functions/checkpoint)** and **[window.history.back()*](https://developer.mozilla.org/en-US/docs/Web/API/Window/history)** functions, this can be emulated.

## Live Example

[Download](snowman_programmaticundo_example.html){: target="_top" download="snowman_programmaticundo_example.html"}

## Twee Code

```twee
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

[Twee Download](snowman_programmaticundo_twee.txt){ target="_top" download="snowman_programmaticundo_twee.txt"}
