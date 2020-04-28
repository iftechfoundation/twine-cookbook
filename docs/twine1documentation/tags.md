# Tags

!!! Warning
    You are reading documentation for Twine 1. The latest version is Twine 2, and very little functionality is backwards compatible.

Sometimes, it can be useful to add information about a passage that isn't visible to readers. Tags are a way to do this – they function as labels stuck on the side of a passage, visible to you while you are writing your story, but they cannot be seen in the published version of your story.

A tag can be any series of letters, numbers, or punctuation without spaces. You can assign as many tags as you like to a passage, as well.

## Special tags

There are some tags that have special meaning to Twine, and change how your story behaves or appears to your readers. These special tags are described below.

- *annotation*: An annotation
- *stylesheet*: A CSS stylesheet. Additional tags (excluding transition) can be applied to restrict this stylesheet to specific passages.
- *transition*: Signifies that the stylesheet defines a CSS transition. Should only appear alongside the stylesheet tag. Has no particular meaning when applied to an ordinary passage.
- *script*: A Javascript script that will be run before the story starts. Used primarily to install custom scripts or macros.
- *bookmark*: A passage that will appear in Sugarcane's Rewind menu
- *nobr*: Causes all of the line breaks in the passage to be removed, as if the entire passage was contained in a `<<nobr>>` macro. Useful if you use a lot of macros.
- *Twine.private*: A passage which will not be included at all in the compiled HTML file
- *startup*: Signifies that the passage can be used to initialize variables. Currently a feature only on Harlowe
