# "Passages in Passages: Snowman (v1.3)

## Summary

In Snowman, the contents of one passage can be included in another through using the *[window.story.render()](https://videlais.github.io/snowman/1/window_story/functions/render.html)* function. This will find and return the source of an existing passage in the story. Combined with the use of Underscore's [template system](https://videlais.github.io/snowman/1/learning/template.html), the returned value can be included directly where the function is used in a passage.

## Live Example

<section>
<iframe src="snowman_passagesinpassages_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_passagesinpassages_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Snowman: Passages in Passages

:: Start
This is the Start passage!
<%= window.story.render("Another") %>

:: Another
And this is Another passage!

```

Download: <a href="snowman_passagesinpassages_twee.txt" target="_blank">Twee Code</a>
