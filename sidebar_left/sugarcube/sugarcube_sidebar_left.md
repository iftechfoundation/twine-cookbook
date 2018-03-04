# "Left Sidebar": SugarCube (v2.18)

## Summary

SugarCube has a built-in left sidebar whose contents can be changed by adding one of several [special passages](http://www.motoslave.net/sugarcube/2/docs/special-names.html#special-passages) to your story.

The following list describes each of the special passages in the order that they appear vertically within the sidebar:

* [StoryBanner](http://www.motoslave.net/sugarcube/2/docs/special-names.html#special-passages-storybanner) appears directly above the story's Title. One use is to show the story's icon/image.
* [StorySubtitle](http://www.motoslave.net/sugarcube/2/docs/special-names.html#special-passages-storysubtitle) appears directly below the story's Title. One use is to show the story's version information.
* [StoryAuthor](http://www.motoslave.net/sugarcube/2/docs/special-names.html#special-passages-storyauthor) is used to show the Author's information.
* [StoryCaption](http://www.motoslave.net/sugarcube/2/docs/special-names.html#special-passages-storycaption) is generally used to show dynamic information about the main character or the story's progress.
* [StoryMenu](http://www.motoslave.net/sugarcube/2/docs/special-names.html#special-passages-storymenu) appears directly above the *Save* button and is used to show custom menu items.
* [StoryShare](http://www.motoslave.net/sugarcube/2/docs/special-names.html#special-passages-storyshare) appears directly below the *Restart* button and is used to access a dialog containing Author's social media or web-site links.

The sidebar can be manually stowed (hidden) and unstowed (revealed) by selecting the **&lt;** or **&gt;** icon in the sidebar's top right corner. The same effect can be achieved programatically by using the [UIBar global object](http://www.motoslave.net/sugarcube/2/docs/api-uibar.html) and its *UIBar.stow()* and *UIBar.unstow()* functions.

## Live Example

<section>
<iframe src="sugarcube_sidebar_left_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_sidebar_left_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Left Sidebar in SugarCube

:: Start
<<set $name to "Jane Doe", $location to "Work">>\
[[Another passage]]


<<link "Stow the sidebar!">>
	<<run UIBar.stow() >>
<</link>>
<<link "Unstow the sidebar!">>
	<<run UIBar.unstow() >>
<</link>>


:: StoryBanner
<img src="https://twinery.org/homepage/img/logo.svg" width="64" height="64">


:: StorySubtitle
Version: 0.2.1


:: StoryAuthor
by Anonymous


:: StoryCaption
Name: $name
Location: $location


:: StoryMenu
[[New story link!|Start]]


:: StoryShare
[[Twinery|https://twinery.org/]]


:: Another passage
<<set $name to "John Smith", $location to "Shop">>\
[[Start]] 
```

Download: <a href="sugarcube_sidebar_left_twee.txt" target="_blank">Twee Code</a>

