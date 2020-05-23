# "Style Markup": Sugarcane (v1.4.2)

!!! Warning
    The following example is designed for Twine 1.4.2.

## Summary

[Style formatting in Twine 1.4.2](https://twinery.org/wiki/twine1:syntax) is supported across all story formats and includes both more basic markup such as emphasis and strong emphasis and the more advanced construction of HTML tables.

## Example

[Download](sugarcane_markup_example.html)

## Twee Code

```twee
:: Start
Italics: //text//
Boldface: ''text''
Underline: __text__
Strikethrough: ==text==
Subscript: H~~2~~O
Superscript: meters/second^^2^^
Comment: /%a comment%/
Error: @@error@@
Inline styling: @@font-weight:bold;text@@
Bulleted list:  
* one
* two
Numbered list:  
# one
# two
!Heading 1
!!Heading 2
!!!Heading 3
!!!!Heading 4
!!!!!Heading 5
!!!!!!Heading 6
|!table header |!table header |!table header |
|row 1|row 1|row 1|
|row 2|row 2|row 2|
|>|row 3|row 3|
|>|>|row 4|
|rows 5 and 6|row 5|row 5|
|~|row 6|row 6|
|rows 7, 8 and 9|>|row 7|
|~|>|row 8|
|~|row 9|row 9|
|table caption|c

:: StoryTitle
Style Markup

:: StoryAuthor
Videlais

```

[Twee Download](sugarcane_markup_twee.txt)
