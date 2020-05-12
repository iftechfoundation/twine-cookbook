# Links

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

Links are the player's means of moving between passages and affecting the story. They are the equivalent of being told to turn to another page in a nonlinear book; in gamebooks, for example, these are clicked to make decisions for the main character. This is not the only possible kind of link.

## Usage

Links are marked like so:

`[[displayed text|title of passage]]`

The two square brackets enclose the whole link, and the pipe symbol separates the displayed text from the passage title.

There is also a shorter form of the link syntax --

`[[passage title]]`

 -- where the displayed link text matches the title of the passage it links to.

If a story has a broken link in it, it is displayed with a red background, and clicking it shows this message:

`The passage 'The newspaper' doesn't exist.`

## External links

Links to external sites can also be added.

```twine1
[[DuckDuckGo|http://www.duckduckgo.com/]]
[[http://www.duckduckgo.com/]]
```

## Setting Variables with Setter-Links

It can be very useful to make certain variables be altered by the act of clicking a link. Inserting an additional square bracket pair into the syntax like so:

`[[displayed text|title of passage][$variable = expression]]`

The 'code' portion of the link syntax is treated as if it was a `<<set>>` macro. A link with a piece of code attached like this is called a *setter link*, and the attached code is called its *tail*.

Much like the `<<set>>` macro, multiple variable-settings by separating either commas or semicolons:

```twine1
* I choose the [[Garb of the Hawk][$hat = "beak"; $shoes = "talons"]]
* I choose the [[Attire of the Mire][$hat = "mud"; $shoes = "gumboots"]]
```

Clicking either of the above links will set both variables simultaneously.

## Printing Links

Setter-links occurs when referred to a variable for any reason other than to set its value. The problem arises because the setter statement is executed with the current values of the variables at the end of the passage - not the values they had when the link statement occurred.

```twine1
<<set $actor to "Fred">>
<if $location[$actor] is passage()>>
[[Talk to <<$actor>>|Talk_Fred][$chat = $actor]]
<<endif>>
<<set $actor to "Ginger">>
<<if $location[$actor] is passage()>>
[[Talk to <<$actor>>|Talk_Ginger][$chat = $actor]]
<<endif>>
```

In this case, regardless of which link, *$chat* would end up getting set to "Ginger" - the value of $actor at the end of the passage.

Although there is a trivial fix that could be used in this example (simply hard code the actors names), the general solution is to use a print macro to write the link statement with the resolved values of the variables:

```twine
<<set $actor to "Fred">>
<<if $location[$actor] is passage()>>
<<print "[[Talk to " + $actor + "|Talk_" + $actor + "][$chat to '" + $actor + "']]">>
<<endif>>
<<set $actor to "Ginger">>
<<if $location[$actor] is passage()>>
<<print "[[Talk to " + $actor + "|Talk_" + $actor + "][$chat to '" + $actor + "']]">>
<<endif>>
```

## Table Syntax

Some shorthand syntax for creating HTML tables exists, and is used like
so:

```twee
| Table header 1 | table header 2 |
| *row 1*        | *row 1*        |
| *row 2*        | *row 2*        |
|*table caption  |
```

The text content of the table is emphasized in the above sample.

> **Note**: The first `|` character in each line does not have any whitespace before it.

## Comments

Comments are used to leave remarks about particular parts of a passage.
They are not displayed when the player views the passage.

## HTML

HTML elements can directly be used in Twine 1:

```html
The sign reads: <div style="padding:1em; border: 1px solid white;">TICKTOCKERSON INSTITUTE OF TEMPORAL FREEZING</div> It hangs in midair, detached from the wall and tilted askew, as if some cosmic video watcher clicked the Pause button as it began to fall.
```

| HTML                       |                              Produces            |
|----------------------------|--------------------------------------------------|
|  \<center\>Text\</center\> |  Horizontally centered text                      |
|  \<span style=\"text-align:right\"\>Text\</span\>   |     Right-aligned text  |
|  \<span style=\"text-align:justify\"\>Text\</span\> |   Fully justified text  |
|  \<small\>Text\</small\>   | Smaller text                                     |
|  \<big\>Text\</big\>       | Bigger text                                      |
|  \<br\>                    | A line break (best used in a [\<\<nobr\>\>] block) |

## Inline Styling

Inline styling is a shorthand way to apply one-off CSS styles to a span
of text.

`<span style="color:magenta;letter-spacing:3px;font-size:1.5em;">Some text</span>`

Becomes:

`@@color:magenta;letter-spacing:3px;font-size:1.5em;Some text@@`

Any text between the first `@@` and the final `;` is usually interpreted
as CSS style properties to apply to the span.

> **Note** Reusing CSS is best done with a passage tagged with `stylesheet`.
