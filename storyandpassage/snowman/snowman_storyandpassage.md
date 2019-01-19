# "Story and Passage API": Snowman (v1.3)

## Summary

Often, it can be useful to access information about the story or other passages while it is running. The [Story](https://twinery.org/wiki/snowman:window-story) and [Passage APIs](https://twinery.org/wiki/snowman:window-passage) in Snowman allow for getting this type of information.

## Live Example

<section>
<iframe src="snowman_storyandpassage_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_storyandpassage_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
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
Download: <a href="snowman_storyandpassage_twee.txt" target="_blank">Twee Code</a>
