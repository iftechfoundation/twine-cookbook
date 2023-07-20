# "Passages in Passages: Snowman (v1.3)

## Summary

In Snowman, the contents of one passage can be included in another through using the **[window.story.render()](https://videlais.github.io/snowman/#/1/window_story/functions/render)** function. This will find and return the source of an existing passage in the story. Combined with the use of Underscore's [template system](https://videlais.github.io/snowman/#/1/learning/template), the returned value can be included directly where the function is used in a passage.

## Example

[Download](snowman_passagesinpassages_example.html){: target="_top" download="snowman_passagesinpassages_example.html"}

## Twee Code

```twee
:: StoryTitle
Snowman: Passages in Passages

:: Start
This is the Start passage!
<%= window.story.render("Another") %>

:: Another
And this is Another passage!

```

[Twee Download](snowman_passagesinpassages_twee.txt){ target="_top" download="snowman_passagesinpassages_twee.txt"}
