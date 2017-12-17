# "Turn Counter": Harlowe (v2.0)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary

"Turn Counter" demostrates the use of the *(history:)* macro in keeping track of "turns" (number of passages visited).

In this example, the *length* of the array returned by using the *(history:)* macro is compared to its modulo 24 value. Sometimes known as "wrap around," the modulus operator (%) is used to get the remainder of the number of "turns" (passages) divided by 24. This creates a clock where its value shows one of a series of strings representing "morning", "mid-morning", "afternoon", or "night."

By visiting other passages, the turn count is increased and the hour reaches 23 before being reset back to 0 before increasing again.

## Live Example

<section>
<iframe src="harlowe_turncounter_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_turncounter_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Turn Counter in Harlowe

:: Start
Rooms:
[[Back Room]]
[[Left Room]]
[[Right Room]]

:: Turn Counter[header]
{
	(set: $hour to (history:)'s length % 24 )
	(if: $hour <= 8)[It is morning.]
	(if: $hour > 8 and $hour <= 12)[It is mid-morning.]
	(if: $hour > 12 and $hour <= 16)[It is afternoon.]
	(if: $hour > 16)[It is night.]
}



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

```

Download: <a href="harlowe_turncounter_twee.txt" target="_blank">Twee Code</a>

