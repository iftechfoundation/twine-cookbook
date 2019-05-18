# "Left Sidebar": Harlowe (only v2.1.0 or later)

## Summary

Harlowe v2.1.0 or later includes a built-in [*named hook*](https://twine2.neocities.org/#markup_named-hook) named *?Sidebar*. When combined with the [*(append:)* macro](https://twine2.neocities.org/#macro_append), dynamic content can be added to the left, blank area containing the default Undo and Redo links. A ["footer" tagged passage](https://twine2.neocities.org/#passagetag_footer) is used to update the dynamic content after each passage transition, and CSS is used to resize and position the existing *tw-sidebar* element.

## Live Example

<section>
<iframe src="harlowe_sidebar_left_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_sidebar_left_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Left Sidebar in Harlowe (v2.1.0 or later)

:: UserStylesheet [stylesheet]
/*
	Reposition the Sidebar 'footer' tagged passage.
*/
tw-sidebar {
	position: fixed;
	top: 0;
	left: 0;
	width: 20%;						/* padding-right of the tw-story element. */
	max-height: 100%;
	margin-top: 5%;					/* padding-top of the tw-story element. */
	padding: 0 0.5em 0.5em 0.5em;
	text-align: right;
	background-color: transparent;
}
tw-icon {
	text-align: right;
	padding-right: 0.75em;
}

:: Start
(set: $name to "Jane Doe", $location to "Work")\
[[Another passage]]

:: Sidebar [footer]
(append: ?SideBar)[\
Name: $name
Location: $location
]

:: Another passage
(set: $name to "John Smith", $location to "Shop")\
[[Start]]
```

Download: <a href="harlowe_sidebar_left_twee.txt" target="_blank">Twee Code</a>

## See Also

[CSS and Passage Tags](../../passagetags/harlowe/harlowe_passagetags.md)
