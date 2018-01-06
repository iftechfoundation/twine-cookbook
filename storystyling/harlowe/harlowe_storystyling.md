# "Variable Story Styling": Harlowe (v2.0)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary

"Variable Story Styling" demonstrates how to combine the *[(background:)](https://twine2.neocities.org/#macro_background)* and *[(color:)](https://twine2.neocities.org/#macro_text-colour)* macros as storied in a variable. Combined with the *[(enchant:)](https://twine2.neocities.org/#macro_enchant)* macro, the named hook [?Page](https://twine2.neocities.org/#markup_named-hook) is used to select the entire page for the application of the background and color changes in each passage.

## Live Example

<section>
<iframe src="harlowe_storystyling_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_storystyling_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Variable Story Styling in Harlowe

:: Start
(set: $storyStyle to (background: white) + (color: green) )
(enchant: ?Page, $storyStyle)
This text is green on a white background.
[[Next Passage]]

:: Next Passage
(set: $storyStyle to (background: black) + (color: white) )
(enchant: ?Page, $storyStyle)
This text is white on a black background.

```

Download: <a href="harlowe_storystyling_twee.txt" target="_blank">Twee Code</a>

