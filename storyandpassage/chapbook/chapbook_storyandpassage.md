# "Story and Passage API": Chapbook (v1.0.0)

## Summary

Often, it can be useful to access information about the story or other passages while it is running. In Chapbook, the *engine.story* object provides two functions, *passageNamed()* and
*passageWithId()*, for accessing other passages. Combined with the [`[JavaScript]` modifier](https://klembot.github.io/chapbook/guide/advanced/using-javascript-in-passages.html), these functions and values they return when given existing passage names, can be used to show the name and source of one passage in another.

## Live Example

<section>
<iframe src="chapbook_storyandpassage_example.html" height=400 width=90%></iframe>


Download: <a href="chapbook_storyandpassage_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Chapbook: Story and Passage API

:: Start
The title of this story is "{story.name}".

The title of this passage is "{passage.name}".

[JavaScript]
	// Find a passage by name
	let storagePassage = engine.story.passageNamed("Storage");
	
	// Write the name
	write('The name of the passage is "' + storagePassage.name + '".<br>');
	
	// Write the source
	write('The name of the passage is "' + storagePassage.source + '".<br>');

:: Storage
This is content in the storage passage!

```
Download: <a href="chapbook_storyandpassage_twee.txt" target="_blank">Twee Code</a>
