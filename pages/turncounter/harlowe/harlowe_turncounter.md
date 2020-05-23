# "Turn Counter": Harlowe (v2.0)

## Summary

"Turn Counter" demonstrates the use of the [`(history:)`](https://twine2.neocities.org/#macro_history) macro in keeping track of "turns" (number of passages visited).

In this example, the *length* of the array returned by using the `(history:)` macro is compared to its modulo 24 value. Sometimes known as "wrap around," the modulus operator (%) is used to get the remainder of the number of "turns" (passages) divided by 24. This creates a clock where its value shows one of a series of strings representing "morning", "mid-morning", "afternoon", or "night."

By visiting other passages, the turn count is increased and the hour reaches 23 before being reset back to 0 before increasing again.

## Example

[Download](harlowe_turncounter_example.html)

## Twee Code

```twee
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

[Twee Download](harlowe_turncounter_twee.txt)
