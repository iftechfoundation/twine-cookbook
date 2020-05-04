# "Story and Passage API": Chapbook (v1.0.0)

## Summary

Often, it can be useful to access information about the story or other passages while it is running. In Chapbook, the *engine.story* object provides two functions, **passageNamed()** and
**passageWithId()**, for accessing other passages. Combined with the [`[JavaScript]`](https://klembot.github.io/chapbook/guide/advanced/using-javascript-in-passages.html) modifier, these functions and values they return when given existing passage names, can be used to show the name and source of one passage in another.

## Example

[Download](chapbook_storyandpassage_example.html)

## Twee Code

```twee
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

[Twee Download](chapbook_storyandpassage_twee.txt)
