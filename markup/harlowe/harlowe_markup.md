# "Style Markup": Harlowe (v2.0)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary

[In Harlowe](https://twine2.neocities.org/#markup_style), style markup can take many forms. Covering italics and boldface as basic examples, Harlowe also provides markup for creating alignment and columns as well.

## Live Example

<section>
<iframe src="harlowe_markup_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_markup_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Style Markup in Harlowe

:: Start
//Italics//
''Boldface''
~~Strikethrough text~~
*Emphasis*
**Strong emphasis**
Super^^script^^
``[[Escaped double square brackets]]``
#Level 1 heading
##Level 2 heading
###Level 3 heading
####Level 4 heading
#####Level 5 heading
######Level 6 heading
* Bulleted item
    *    Bulleted item 2
  ** Indented bulleted item
 0. Numbered item
   0. Numbered item 2
 0.0. Indented numbered item
 ==>
This is right-aligned
  =><=
This is centered
 <==>
This is justified
<==
This is left-aligned (undoes the above)
===><=
This has margins 3/4 left, 1/4 right
  =><=====
This has margins 1/6 left, 5/6 right.
|==
This is in the leftmost column, which has a right margin of about 2 letters wide.
    =|||=
This is in the next column, which has margins of 1 letter wide. It is three times as wide as the left column.
 =====||
This is in the right column, which has a right margin of about 5 letters wide. It is twice as wide as the left column.
  |==|
This text is not in columns, but takes up the entire width, as usual.

```

Download: <a href="harlowe_markup_twee.txt" target="_blank">Twee Code</a>

