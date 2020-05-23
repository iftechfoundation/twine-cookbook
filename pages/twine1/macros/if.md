# `<<if>>`

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

The `<<if>>` macro is used to control what text the player sees when they visit a passage, or what macros are run when the passage loads.

## Usage

The `<<if>>` macro can be used in formats like these:

```twee
<<if expression>> Text <<endif>>
<<if expression>> Text <<else>> Text <<endif>>
<<if expression>> Text <<else if expression>> Text... <<endif>>
```

*expression* is an expression that can evaluate to true or false. Text is any amount of passage text that you wish to display only if the condition is true. `<<endif>>` is a macro tag indicating the end of the `<<if>>` macro invocation.

Note that the Text can contain any Twine code, including an inner `<<if>>` invocation:

```twee
<<if $body is "wounded">>You are <<if $blood <= 5>>about to die<<else>>bleeding<<endif>>. Seek help!<<endif>>
```

## Motivating example

Consider a passage like this:

> You return to Selator's hut. A merry fire is crackling in the kitchen, and something is cooking that smells delicious. He greets you warmly and asks, “Have you got the berry?” If you have got the purple berry of the Antherica plant, turn to 175. If not, turn to 52.
>
> (Steve Jackson and Ian Livingstone, Scorpion Swamp)

It would be nice if the story could track whether the protagonist found the berry or not, and branch accordingly. We can do this by simply noting the name of the passage where the berry was found:

```twee
:: Antherica
You have no doubt, from Selator's description, that you have found the
Antherica plant. Half your mission is completed. Now you must return to the village with the precious berry.
```

Then we can use the `<<if>>` macro and the visited() function to display a passage indicating victory:

```twee
You return to Selator's hut. A merry fire is crackling in the kitchen, and
something is cooking that smells delicious. He greets you warmly and asks,
"Have you got the berry?"

<<if visited("Antherica")>>
"Wonderful!" he exclaims...
<<endif>>
```

## A note about line breaks

When a passage containing an `<<if>>` macro is displayed, the `<<if>>` and `<<endif>>` macro tags are removed from the text. But, the line on which the tags was placed will remain - thus, if it was by itself on a line, it will create a blank line. You can choose to fix this by ending the tags' lines with a backslash:

```twee
You leap over the sawblade with deft ease.
<<if $alive>>\
She laughs. "Still not dead? How callous of you to scorn Death's loving embrace!"
<<endif>>\
```

You may, for larger `<<if>>` constructions, use the `<<nobr>>` macro instead:

```twee
You glare at the alien control panel. <<nobr>>
<<if $red>>
The red button blinks <<if $earplugs>> and hisses<<endif>> at you.
<<endif>>
<<endnobr>>
```
