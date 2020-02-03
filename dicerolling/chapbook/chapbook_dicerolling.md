# "Dice Rolling": Chapbook (v1.0)

## Summary

This example demonstrates how to create the same effects of rolling various physical dice through using the *[random](https://klembot.github.io/chapbook/guide/state/randomness.html)* global variable in Chapbook.

[Inserts](https://klembot.github.io/chapbook/guide/modifiers-and-inserts/) are used to display the use of *random* in the passage. For calculations, a [var section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) and temporary variables are used because expressions cannot be used within inserts.

## Live Example

<section>
<iframe src="chapbook_dicerolling_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_dicerolling_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Chapbook: Rolling Dice

:: Start
_example1: random.d4 + 4
_example2: random.d6 - 2
_example3: random.d6 + random.d6 + 10
--

Rolling a 1d4: {random.d4}

Rolling a 1d6: {random.d6}

Rolling a 1d8: {random.d8}

Rolling a 1d10: {random.d10}

Rolling a 1d12: {random.d12}

Rolling a 1d20: {random.d20}

Rolling a 1d100: {random.d100}

Rolling a 1d4 + 4: {_example1}

Rolling a 1d6 - 2: {_example2}

Rolling a 2d6 + 10: {_example3}

```

Download: <a href="chapbook_dicerolling_twee.txt" target="_blank">Twee Code</a>
