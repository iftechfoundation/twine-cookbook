# "Turn Counter": Chapbook (v1.0.0)

## Summary

In Chapbook, the global variable *trail* stores all of the passages visited as an increasing array. For each passage visited, a new entry is added.

Sometimes known as "wrap around," the modulus operator (%) is used to get the remainder of the number of "turns" (number of passages) divided by 24. This creates a clock where its value shows one of a series of strings representing "morning", "mid-morning", "afternoon", or "night."

By visiting other passages, the turn count is increased and the hour reaches 23 before being reset back to 0 before increasing again.

## Example

[Download](chapbook_turncounter_example.html){ target="_top" download="chapbook_turncounter_example.html"}

## Twee Code

```twee
:: StoryTitle
Chapbook: Turn Counter

:: Start
hour: trail.length % 24
--
{embed passage: "Turn Counter"}
Rooms:

[[Back Room]]

[[Left Room]]

[[Right Room]]


:: Back Room
{embed passage: "Turn Counter"}
Rooms:

[[Left Room]]

[[Right Room]]

[[Front Room|Start]]


:: Left Room
{embed passage: "Turn Counter"}
Rooms:

[[Right Room]]

[[Back Room]]

[[Front Room|Start]]


:: Right Room
{embed passage: "Turn Counter"}
Rooms:

[[Left Room]]

[[Back Room]]

[[Front Room|Start]]


:: Turn Counter
hour: trail.length % 24
--
[if hour <= 8]
  It is morning.

[if hour > 8 && hour <= 12]
  It is mid-morning.

[if hour > 12 && hour <= 16]
  It is afternoon.

[if hour > 16]
  It is night.

```

[Twee Download](chapbook_turncounter_twee.txt){ target="_top" download="chapbook_turncounter_twee.txt"}
