# How do I make links?

A link is a connection between one passage and another, both visually in Twine 2 and as a hyperlink a user can click to navigate to a passage of the same name in the published HTML.

## Passage Link

When something is enclosed within the two sets of opening and closing square brackets, this "links" one passage to another of that exact word or phrase. The "link" is the name of that other passage.

For example, the code below links to the passage named "Example":
```
[[Example]]
```

When using Twine 2, it will automatically create the passage if it does not exist when linked from another passage. The [Passages View](../introduction/twine2_passages_view.md) shows the links between them.

## Routing Links

It is also possible to "route" links to different passages. Arrows, `->` or `<-`, can be used to point to the destination of the link and "away" from the word or phrase used as the link text.

```
[[Link to another passage->Different Passage Name]]

[[Different Passage Name<-Link to another passage]]
```

The pipe character, `|`, can also be used to route a user to a different passage than shown in the hyperlink.

For example, the code below routes to the passage "Another" rather than "Example" as it would show:
```
[[Example|Another]]
```
