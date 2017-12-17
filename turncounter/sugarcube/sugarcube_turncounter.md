# "Turn Counter": SugarCube (v2.18)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary

"Turn Counter" demostrates the use of the *[State.turns](http://www.motoslave.net/sugarcube/2/docs/api-state.html)* attribute of the *State* object to keep track of the "turns" (moments within the story).

In this example, the *State.turns* attribute is compared to its modulo 24 value. Sometimes known as "wrap around," the modulus operator (%) is used to get the remainder of the number of "turns" (moments) divided by 24. This creates a clock where its value shows one of a series of strings representing "morning", "mid-morning", "afternoon", or "night."

This example also uses the special name "[PassageHeader](http://www.motoslave.net/sugarcube/2/docs/special-names.html#special-passages)" as a named passage that is prepended to each passage in the story. The results of the modulo 24 calculation and clock string is displayed on every passage. By visiting other passages, the turn count is increased and the hour reaches 23 before being reset back to 0 before increasing again.

## Live Example

<section>
<iframe src="sugarcube_turncounter_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_turncounter_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
SugarCube: Turn Counter

:: Start

Rooms:
[[Back Room]]
[[Left Room]]
[[Right Room]]

:: Back Room

Rooms:
[[Left Room]]
[[Right Room]]
[[Front Room|Start]]

:: Left Room

Rooms:
[[Right Room]]
[[Back Room]]
[[Front Room|Start]]

:: Right Room

Rooms:
[[Left Room]]
[[Back Room]]
[[Front Room|Start]]

:: PassageHeader
<<set $hour to State.turns % 24>>
<<if $hour <= 8>>It is morning.<</if>>
<<if $hour > 8 and $hour <= 12>>It is mid-morning.<</if>>
<<if $hour > 12 and $hour <= 16>>It is afternoon.<</if>>
<<if $hour > 16>>It is night.<</if>>


```

Download: <a href="sugarcube_turncounter_twee.txt" target="_blank">Twee Code</a>

