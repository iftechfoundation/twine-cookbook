# "Passage Visits": Chapbook (v1.0.0)

## Summary

In Chapbook, the [lookup](https://klembot.github.io/chapbook/guide/state/objects-and-lookups.html) *passage.visits* variable contains the number of times the current passages has been visited by the user.

## Live Example

<section>
<iframe src="chapbook_passagevisits_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_passagevisits_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Chapbook: Passage Visits

:: Start

[[Another Passage]]

:: Another Passage
How many times has the current passage been visited? {passage.visits}

[[Start]]


```

Download: <a href="chapbook_passagevisits_twee.txt" target="_blank">Twee Code</a>
