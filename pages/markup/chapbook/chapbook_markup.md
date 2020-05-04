# "Style Markup": Chapbook (v1.0.0)

!!! Information
    The [Text Formatting](https://klembot.github.io/chapbook/guide/text-and-links/text-formatting.html) section of the [Chapbook Guide](https://klembot.github.io/chapbook/guide/) states you can also use a &#35; character to indicate a Numbered List item. This currently (as of v1.0.0-beta) isn't correct, as that character actually results in a Level 1 Header.

## Summary

Chapbook uses a customized sub-set of [Markdown](https://guides.github.com/features/mastering-markdown/) to support its style formatting.

## Example

[Download](chapbook_markup_example.html)

## Twee Code

```twee
:: StoryTitle
Style Markup in Chapbook

:: Start
*Emphasis (aka Italics)* or _using single underscores_ <br>
**Strong Emphasis (aka Bold)** or __using double underscores__ <br>
Combined Emphasis with **asterisks and _underscores_** <br>
<del>Strikethrough text</del> <br>
Super<sup>script</sup> <br>
Sub<sub>script</sub> <br>
`Monospaced Type (aka Code Block)` <br>
~~Small Caps~~
<blockquote>Quote</blockquote>

* A Bulleted list item (using asterisk)
* Another Bulleted list item (using asterisk)
- A Bulleted list item (using minus)
- Another Bulleted list item (using minus)
+ A Bulleted list item (using plus)
+ Another Bulleted list item (using plus)

1. A Numbered list item
2. Another Numbered list item

[align left]
Text is left-aligned.
[align center]
Text is centered / centred.
[align right]
Text is right-aligned.
[Continue]
Text-alignment has been reset to the default.

Ignoring of \*Formatting\* Characters <br>
More ignoring of \_\_Formatting\_\_ Characters


Above Section Break is Chapbook specific or standard HTML...
***
Below Section Break is supported Markdown extras...

# Level 1 Heading
## Level 2 Heading
### Level 3 Heading
#### Level 4 Heading
##### Level 5 Heading
###### Level 6 Heading

Alternative Level 1 Heading
======
Alternative Level 2 Heading
------

| Table mark-up  | with      | alignment  |
| ---      | :---:      | ---:    |
| column 1 is  | left-aligned  | 1      |
| col 2 is    | centered      | 10    |
| col 3 is    | right-aligned  | 100    |

```

[Twee Download](chapbook_markup_twee.txt)
