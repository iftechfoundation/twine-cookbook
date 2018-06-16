# Passages

Passages can be thought of as divisions of time, space, or combinations of the two. They can also be thought of as blocks of dialogue, sections of code, or simply ways to break up a complicated project into more easily understood parts. In Twine, passages are at the core of any [story](../terms/terms_stories.md).

## Connecting Passages

The simplest way to connect passages is through adding two opening and closing brackets around any collection of letters, numbers, or punctuation. If a passage exists with those exact characters in the same ordering and combination, the passages will be linked together. When viewing the compiled HTML version, there will now be a link to navigate between the two.

By default, passage links are one-way. Navigating the link means moving away from one to another.

### Link to Another Passage named "Link to another passage":

```
[[Link to another passage]]
```

### Link to Another Passage Named "Different Passage":

The pipe, "`|`", can be used to rename a link from its original to some other name for the same purpose.

```
[[Link to another passage|Different Passage]]
```

### Link to Another Passage Named "Different Passage":

Starting in Twine 2, to route links, arrows, "->" or "<-", can be used to *point* to the destination of the link.

```
[[Link to another passage->Different Passage]]
```

```
[[Different Passage<-Link to another passage]]
```
