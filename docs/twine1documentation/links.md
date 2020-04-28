# Links

!!! Warning
    You are reading documentation for Twine 1. The latest version is Twine 2, and very little functionality is backwards compatible.

Links are the player's means of moving between passages and affecting the story. They are the equivalent of being told to turn to another page in a nonlinear book; in gamebooks, for example, you do this to make decisions for the main character. But this isn't the only possible kind of link.

## Usage

Links are marked like so:

`[[displayed text|title of passage]]`

The two square brackets enclose the whole link, and the pipe symbol separates the displayed text from the passage title.

There is also a shorter form of the link syntax --

`[[passage title]]`

 -- where the displayed link text matches the title of the passage it links to.

If a story has a broken link in it, it is displayed with a red background in your story, and clicking it shows this message:

`The passage 'The newspaper' doesn't exist.`

## External links

You may also add links to external sites. These links look like this:

```twine1
[[DuckDuckGo|http://www.duckduckgo.com/]]
[[http://www.duckduckgo.com/]]
```

You may link to any address that a reader's web browser will understand.

## Setting variables with Setter-Links

When you develop more complex stories that use variables, it can be very useful to make certain variables be altered by the act of clicking a link. You can accomplish this by inserting an additional square bracket pair into the syntax like so:

`[[displayed text|title of passage][$variable = expression]]`

The 'code' portion of the link syntax is treated as if it was a `<<set>>` macro - consult that page to learn about the syntax to use. A link with a piece of code attached like this is called a setter link, and the attached code is called its tail.

Much like the `<<set>>` macro, you can chain together multiple variable-settings by separating them with either commas or semicolons:

```twine1
* I choose the [[Garb of the Hawk][$hat = "beak"; $shoes = "talons"]]
* I choose the [[Attire of the Mire][$hat = "mud"; $shoes = "gumboots"]]
```

Clicking either of the above links will set both variables simultaneously.

## Printing Links

With very complex stories you may come across an issue with setter-links that occurs when you refer to a variable for any reason other than to set its value. The problem arises because the setter statement is executed with the current values of the variables at the end of the passage - not the values they had when the link statement occurred.

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

In this case, regardless of which link you picked, *$chat* would end up getting set to "Ginger" - the value of $actor at the end of the passage.

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
