# "Setting and Showing Variables": Harlowe (v2.0)

## Summary

Variables, symbols starting with ```$``` (for story-wide variables) or ```_``` (for temporary passage variables), can be "set" using the *[(set:)](https://twine2.neocities.org/#macro_set)* macro in Harlowe. ```$``` should be used for data you wish to store throughout the story, and ```_``` should be used for data you only need in the current passage. Using ```_``` is good whens you don't want to accidentally overwrite variables elsewhere in the story, and can help with debugging by not cluttering up the variables list of future passages.

The keyword ```it``` can also be used as a shortcut for changing and saving a value in reference to itself. The ```it``` refers to the first variable named in the macro.

## Live Example

<section>
<iframe src="harlowe_settingandshowing_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_settingandshowing_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Setting and Showing Variables in Harlowe

:: Start
(set: $numberVariable to 5)
(set: $textVariable to "five")
(set: _textVariable to "The values")

_textVariable are $numberVariable and $textVariable.

(set: $numberVariable to it + 1)

_textVariable are $numberVariable and $textVariable.
```

Download: <a href="harlowe_settingandshowing_twee.txt" target="_blank">Twee Code</a>

