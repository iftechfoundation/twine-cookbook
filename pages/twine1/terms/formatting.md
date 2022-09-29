# Formatting

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

Special characters can be applied to text to change its formatting.

| Formatting     | Source Code               | Appears As                          | Resulting HTML                                 |
| -------------- | ------------------------- | ----------------------------------- | ---------------------------------------------- |
| Italics        | `//text//`                  | *text*                              | `<em>text</em\> `                             |
| Boldface       | `''text''`                  | **text**                            | `<strong>text</strong\>`                      |
| Underline      | `__text__`              | <span class="underline">text</span> | `<u>text</u\>`                                |
| Strikethrough  | `==text==`                 | ~~text~~                            | `<strike>text</strike\>   `                   |
| Subscript      | `H~~2~~O`               | H<sub>2</sub>O                      | `H<sub>2</sub>O`                           |
| Superscript    | `meters/second^^2^^`        | meters/second<sup>2</sup>           | `meters/second<sup\>2</sup\>`                  |
| Monospace      | `{{{a //word//}}}`          | `a //word//`                        | `<code>a //word//</code\>`                    |
| Comment        | `/%a comment%/`             |                                     |                                                |
| Error          | `@@error@@`                 | **error**                           | `<span class="marked">error</span\>  `          |
| Inline styling | `@@font-weight:bold;text@@` | **text**                            | `<span style="font-weight:bold">text</span\>` |

## Additional Syntax

|Formatting|Source Code|Resulting HTML|
|---------------|---------------|-----------------------------------|
|Bulleted list  | `* one * two` |`<ul><li>one</li><li>two</li></ul>`|
|Numbered list  | `# one # two` |`<ol><li>one</li><li>two</li></ol>`|
|Horizontal line| `----`        |`<hr>`                             |
|Indented text  | `>Text`       |`<blockquote>Text</blockquote>`    |
|Doubly indented text| `>>Text` |`<blockquote><blockquote>Text</blockquote></blockquote>`|
|Heading 1      | `!Title`      |`<h1>Title</h1>`                   |
|Heading 2      | `!!Title`     |`<h2>Title</h2>`                   |
|Heading 3      | `!!!Title`    |`<h3>Title</h3>`                   |
|Heading 4      | `!!!!Title`   |`<h4>Title</h4>`                   |
|Heading 5      | `!!!!!Title`  |`<h5>Title</h5>`                   |

## Escaped Line Breaks

One extra piece of syntax, separate from the above tables, is available:
ending a line with a backslash `\` will cause both the backslash and the
line break to be removed from the passage, thus "joining together" both
lines. The main purpose of this will become apparent when you use macros.
