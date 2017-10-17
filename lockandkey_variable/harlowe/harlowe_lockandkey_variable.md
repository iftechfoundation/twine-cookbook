# "Lock and Key: Variable": Harlowe (v2.0)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

<div class="alert information"><strong>This recipe is affected by history changes in the story.</strong> Undoing or re-doing back to a passage containing this recipe has the potential to change its saved values.</div>

## Summary

"Lock and Key: Variable" demostrates how to create the effect of picking up a key and unlocking a door. In this example, the key is a variable (*$key*) and is initially set to the value *false* in the Start passage.

When the link "Pick up the key" is clicked, *$key* is changed to the value *true* and the door link changes from its initial response of "*Locked Door*" to a link to the passage Exit.

## Live Example

<section>
<iframe src="harlowe_lockandkey_variable_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_lockandkey_variable_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Lock and Key: Variable in Harlowe

:: Start
(set: $key to false)

Rooms:
[[Front Room]]
[[Back Room]]

:: Front Room
(if: $key is true)[
	[[Exit]]
]
(else:)[
	*Locked Door*
]

Rooms:
[[Back Room]]

:: Back Room
(if: $key is false)[
	Items:
	(link: "Pick up key")[(set: $key to true)You have a key.]
]
(else:)[
	There is nothing here.
]

Rooms:
[[Front Room]]

:: Exit
You found the key and went through the door!

```

Download: <a href="harlowe_lockandkey_variable_twee.txt" target="_blank">Twee Code</a>

