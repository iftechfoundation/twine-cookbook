# "Cycling Choices": Harlowe (v2.0)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary

"Cycling Choices" demostrates how to create a 'cycling' effect of different choices through clicking on them. 

The 'cycle' starts with the use of the *(display:)* macro and assumption of *$choicesCount* beginning at the number 0. It is then increased by one to the value 1 (the first location of an array in Harlowe) and the position of *$choices* is shown based on this. 

If the user clicks on the link (created through using the *(link:)* and *(display:)* macros) again, future 'cycles' test if *$choicesCount* increases beyond the number of values in the *$choices* array and resets it to 1. 

At the end of every 'cycle,' the currently selected value is stored in the variable *$cyclingResult* for future access and usage.

## Live Example

<section>
<iframe src="harlowe_cycling_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_cycling_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Cycling Choices in Harlowe

:: Start
Click options to cycle: (display: "Cycling")
[[Submit|Results]]

:: Cycling
{
	(set: $choices to (array: "First", "Second", "Third") )
	(if: $choicesCount >= $choices's length)[(set: $choicesCount to 1)]
	(else:)[(set: $choicesCount to it + 1)]
	(set: $cyclingResult to $choices's $choicesCount)
	(link: (text: $choices's $choicesCount) )[(display: "Cycling")]
}

:: Results
$cyclingResult
```

Download: <a href="harlowe_cycling_twee.txt" target="_blank">Twee Code</a>

