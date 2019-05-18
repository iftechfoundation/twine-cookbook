# "Left Sidebar": Harlowe (both v1.x and v2.x series)

## Summary

Harlowe has a built-in left sidebar. Before v2.1.0, however, there was no functionality to add dynamic content. It is possible to re-purpose a ["footer" tagged passage](https://twine2.neocities.org/#passagetag_footer) to act as a custom sidebar to display dynamic content below Harlowe's own sidebar.

## Twee Code

```
:: StoryTitle
Left Sidebar in Harlowe


:: UserStylesheet [stylesheet]
/*
	Reposition the Sidebar 'footer' tagged passage.
*/
tw-include[title="Sidebar"] {
	position: fixed;
	top: 0;
	left: 0;
	width: 20%;						/* padding-right of the tw-story element. */
	max-height: 100%;
	margin-top: calc(5% + 171px);	/* padding-top of the tw-story element plus computed height of the tw-sidebar element. */
	padding: 0.5em;
	background-color: transparent;
	text-align: right;
}


:: Start
(set: $name to "Jane Doe", $location to "Work")\
[[Another passage]]


:: Sidebar [footer]
Name: $name
Location: $location


:: Another passage
(set: $name to "John Smith", $location to "Shop")\
[[Start]]


```

## See Also

[CSS and Passage Tags](../../passagetags/harlowe/harlowe_passagetags.md)
