# "Story and Passage API": Snowman (v1.4)

## Summary

Often, it can be useful to access information about the story or other passages while it is running. The [**window.story.passage()**](https://videlais.github.io/snowman/#/1/window_story/functions/passage) function and *[window.passage.name](https://videlais.github.io/snowman/#/1/window_story/properties/name)* property in Snowman allow for getting this type of information.

## Example

[Download](snowman_storyandpassage_example.html){: target="_top" download="snowman_storyandpassage_example.html"}

## Twee Code

```twee
:: StoryTitle
Story and Passage API in Snowman

:: Start
The title of this story is "<%= window.story.name %>."

<%
  window.setup = {};
  window.setup.passage = window.story.passage("Storage");
%>

The name of the passage is "<%= setup.passage.name %>."

The source of the passage is "<%= setup.passage.source %>"

:: Storage
This is content in the storage passage!

```

[Twee Download](snowman_storyandpassage_twee.txt){ target="_top" download="snowman_storyandpassage_twee.txt"}
