# "Sidebar": Harlowe (v2.0)

## Summary

Harlowe does have a built-in sidebar. However, one can be created through using the [*(css:)*](https://twine2.neocities.org/#macro_css) and [*(display:)*](https://twine2.neocities.org/#macro_display) macros to position and set a background color for a hook while also having its contents be another passage. Through using the ['header' passage-tag](https://twine2.neocities.org/#passagetag_header), this created sidebar can also be included in every passage.

## Live Example

<section>
<iframe src="harlowe_sidebar_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_sidebar_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Sidebar in Harlowe

:: Start
[[Another passage]]

:: Header[header]
(css:"
	background-color: #222;
	border-right: 1px solid #444;
	position: fixed;
	top: 0;
	right: 0;
	width: 20%;
	height: 100%;
	margin: 0;
	padding: 0.5em;
  ")[(display: "Sidebar")]

:: Sidebar

This is the sidebar!

:: Another passage
[[Start]]

```

Download: <a href="harlowe_sidebar_twee.txt" target="_blank">Twee Code</a>

