# Tags

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

Sometimes, it can be useful to add information about a passage that is not visible to readers. Tags are a way to do this. They function as labels stuck on the side of a passage, visible to only the author while writing.

A tag can be any series of letters, numbers, or punctuation without spaces. Passages can have multiple tags.

## Special tags

There are some tags that have special meaning to Twine. They change how the story behaves or appears. These special tags are described below.

- *annotation*: An annotation
- *stylesheet*: A CSS stylesheet. Additional tags (excluding transition) can be applied to restrict this stylesheet to specific passages.
- *transition*: Signifies that the stylesheet defines a CSS transition. Should only appear alongside the stylesheet tag. Has no particular meaning when applied to an ordinary passage.
- *script*: A JavaScript script that will be run before the story starts. Used primarily to install custom scripts or macros.
- *bookmark*: A passage that will appear in Sugarcane's Rewind menu
- *nobr*: Causes all of the line breaks in the passage to be removed, as if the entire passage was contained in a `<<nobr>>` macro.
- *Twine.private*: A passage which will not be included at all in the compiled HTML file
- *startup*: Signifies that the passage can be used to initialize variables. Currently a feature only on Harlowe
