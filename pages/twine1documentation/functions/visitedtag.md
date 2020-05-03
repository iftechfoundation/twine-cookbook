# *visitedTag(string, string...)*

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

Has a value equal to the number of times you've visited passages with the given tags. If you use tags to delineate parts of your story, this can be a useful variant of *visited()*.

```twee
Hard to believe you spent <<print visitedTag("Swamp")>> turns inside the swamp!

<<if visitedTag("church","death")>>\
You died in the church, for some reason.
<<endif>>\
```
