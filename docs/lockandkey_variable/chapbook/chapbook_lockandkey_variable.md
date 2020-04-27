# "Lock and Key: Variable": Chapbook (v1.0.0)

## Summary

"Lock and Key: Variable" demonstrates how to create the effect of picking up a key and unlocking a door. In this example, the key is a variable (*key*) and is initially set to the value "false" in the Start passage.

When the link "Pick up key" is clicked in the "Back Room" passage, *key* is changed to the value "true" via embedding the passage "Key". When the passage is visited and *key* is set to the value of "true", door link changes from its initial response of "Locked Door" to "Unlock the door".

## Live Example

<section>
<iframe src="chapbook_lockandkey_variable_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_lockandkey_variable_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```twee
:: StoryTitle
Chapbook: Lock and Key: Variable

:: Start
key: false
--

Rooms:

[[Front Room]]

[[Back Room]]


:: Front Room
[if key == true]
	[[Unlock the door->Exit]]
[else]
	*Locked Door*
[continued]

Rooms:

[[Back Room]]


:: Back Room
[if key == false]
	Items:
	{reveal link: 'Pick up key', passage: 'Key'}
[else]
	There is nothing here.
[continued]

Rooms:

[[Front Room]]

:: Exit
You found the key and went through the door!

:: Key
key: true
--
You picked up the key!

```

Download: <a href="chapbook_lockandkey_variable_twee.txt" target="_blank">Twee Code</a>
