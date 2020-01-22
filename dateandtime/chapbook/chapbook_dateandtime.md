# "Date and Time": Chapbook (1.0.0)

## Summary

Using the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html), different values can be set in Chapbook. In this example, a new [Date object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) is created in JavaScript and the result of its functions are saved before using expressions to show them.

## Live Example

<section>
<iframe src="chapbook_dateandtime_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_dateandtime_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Date and Time in Chapbook

:: Start
date: new Date()
month: date.getMonth()
day: date.getDay()
year: date.getFullYear()
--

The current month number is {month}.

The current day number is {day}.

The current full-year number is {year}.

```
Download: <a href="chapbook_dateandtime_twee.txt" target="_blank">Twee Code</a>
