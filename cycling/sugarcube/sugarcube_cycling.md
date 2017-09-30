# "Cycling Choices": SugarCube (v2.18)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary

"Cycling Choices" demostrates how to create a 'cycling' effect of different choices through clicking on them. 

The 'cycles' starts with the use of the *&lt;&lt;include&gt;&gt;* macro and assumption of *$choicesCount* beginning at the number -1. Within the passage "Cycling", the first 'cycle' begins with testing if the variable *$choices* exists in the story through using the *State.variables* object. If it does not, *$choices* and *$choicesCount* are set (created) to their initial values.

Next, *$choicesCount* is then increased by one to the start value of 0 (the first location of an array in SugarCube) and the position of *$choices* is shown based on this. 

If the user clicks on the link (created through using the *&lt;&lt;linkreplace&gt;&gt;* and *&lt;&lt;include&gt;&gt;* macros) again, future 'cycles' test if *$choicesCount* increases beyond the number of values in the *$choices* array and resets it to 0. 

At the end of every 'cycle,' the currently selected value is stored in the variable *$cyclingResult* for future access and usage.

## Live Example

<section>
<iframe src="sugarcube_cycling_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_cycling_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Cycling Choices in SugarCube

:: Start
Click options to cycle: <<include "Cycling">>
[[Submit|Results]]

:: Cycling
\<<if !State.variables["choices"]>>
\	<<set $choicesCount to -1>>
\	<<set $choices to ["First", "Second", "Third"]>>
\<</if>>
\
\<<set $choicesCount to $choicesCount + 1>>
\
\<<if $choicesCount >= $choices.length>>
\ 	<<set $choicesCount to 0>>
\<</if>>
\
\<<set $cyclingResult to $choices[$choicesCount]>>
\
\<<linkreplace $choices[$choicesCount]>><<include "Cycling">><</linkreplace>>

:: Results
$cyclingResult

```

Download: <a href="harlowe_cycling_twee.txt" target="_blank">Twee Code</a>

