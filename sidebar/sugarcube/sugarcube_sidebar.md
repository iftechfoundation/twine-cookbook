# "Sidebar": SugarCube (v2.18)

## Summary

SugarCube has a built-in sidebar. Using the [UIBar global object](http://www.motoslave.net/sugarcube/2/docs/api-uibar.html) and its *UIBar.stow()* and *UIBar.unstow()* functions, the sidebar can be hidden and revealed. Additional menu links can also be added through using the ["StoryMenu" passage-tag](http://www.motoslave.net/sugarcube/2/docs/special-names.html#special-passages-storymenu). Links found in the tagged passage allow direct navigation to their target locations within the story.

## Live Example

<section>
<iframe src="sugarcube_sidebar_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_sidebar_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Sidebar in SugarCube

:: Start
<<link "Stow the sidebar!">>
	<<run UIBar.stow() >>
<</link>>

<<link "Unstow the sidebar!">>
	<<run UIBar.unstow() >>
<</link>>

:: StoryMenu[StoryMenu]
[[New story link!|Start]]

```

Download: <a href="sugarcube_sidebar_twee.txt" target="_blank">Twee Code</a>

