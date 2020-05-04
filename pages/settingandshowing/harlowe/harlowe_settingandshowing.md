# "Setting and Showing Variables": Harlowe (v2.0)

## Summary

Variables, symbols starting with `$` (for story-wide) or `_` (for temporary), can be "set" using the [`(set:)`](https://twine2.neocities.org/#macro_set) macro in Harlowe.

`$` is used for storing data throughout the story, and `_` should be used for data only needed in the current passage. Using `_` is useful for not wanting to accidentally overwrite variables elsewhere in the story. They can also help with debugging through not cluttering up the variables list of future passages.

In Harlowe, the keyword **it** can also be used as a shortcut for changing and saving a value in reference to itself. The **it** refers to the first variable named in the macro.

## Example

[Download](harlowe_settingandshowing_example.html)

## Twee Code

```twee
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

[Twee Download](harlowe_settingandshowing_twee.txt)
