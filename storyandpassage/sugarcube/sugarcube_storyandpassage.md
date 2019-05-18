# "Story and Passage API": SugarCube (v2.18)

## Summary

Often, it can be useful to access information about the story or other passages while it is running. The [Story](https://www.motoslave.net/sugarcube/2/docs/#story-api) and [Passage APIs](https://www.motoslave.net/sugarcube/2/docs/#passage-api) in SugarCube allow for getting this type of information.

## Twee Code

```
:: StoryTitle
Story and Passage API in SugarCube

:: Start
The title of this story is "<<print Story.title >>."

<<set $passage to Story.get("Storage")>>

The title of the passage is "<<print $passage.title>>."

The text of the passage is "<<print $passage.text >>"


:: Storage
This is content in the storage passage!

```
