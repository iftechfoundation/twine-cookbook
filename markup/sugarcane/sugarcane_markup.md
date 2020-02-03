# "Style Markup": Sugarcane (v1.4.2)

<div class="alertbox warning"><strong>Note:</strong> The following example is designed for Twine 1.4.2.</div>

## Summary

[Style formatting in Twine 1.4.2](https://twinery.org/wiki/twine1:syntax) is supported across all story formats and includes both more basic markup such as italics and bolds and the more advanced construction of HTML tables.

## Live Example

<section>
<iframe src="sugarcane_markup_example.html" height=400 width=90%></iframe>

Download: <a href="sugarcane_markup_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: Start
Italics: //text//
Boldface: ''text''
Underline: __text__
Strikethrough: ==text==
Subscript: H~~2~~O
Superscript: meters/second^^2^^
Escaped: {{{a //word//}}}
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

Download: <a href="sugarcane_markup_twee.txt" target="_blank">Twee Code</a>

