# Passages

Passages can be thought of as divisions of time, space, or combinations of the two. They can also be thought of as blocks of dialogue, sections of code, or simply ways to break up a complicated project into more easily understood parts. In Twine, passages are at the core of any [Story](../terms/terms_stories.md). They are the building blocks of everything that Twine is and can be.

# Connecting Passages

The simplest way to connect Passages is through adding two opening and closing brackets around any collection of letters, numbers, or punctuation. If a passage exists with those exact characters in the same ordering and combination, the passages will be linked together. When viewing the compiled HTML version, there will now be a link to navigate between the two, sending the player from one passage to another.

By default, links are one-way. Navigating the link usually means moving away from one Passage to another in the Story. Additional code can be also added to the link to make it appear in different ways.

**Link to Another Passage named "Link to another passage":**
```
[[Link to another passage]]
```
To route links, arrows, "->" or "<-", can be used to *point* to the destination of the link. When navigated, the player will go to that next passage.

**Link to Another Passage Named "Different Passage":**
```
[[Link to another passage->Different Passage]]
```

**Link to Another Passage Named "Different Passage":**
```
[[Different Passage<-Link to another passage]]
```

The pipe, "|", can also be used to rename a link from its original to some other name for the same purpose.

**Link to Another Passage Named "Different Passage":**
```
[[Link to another passage|Different Passage]]
```

While originally introduced in different story formats, both forms, arrows and pipes, are now supported by all three story formats.
