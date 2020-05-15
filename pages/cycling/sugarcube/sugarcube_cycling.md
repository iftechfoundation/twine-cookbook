# "Cycling Choices": SugarCube (v2.18)

## Summary

"Cycling Choices" demonstrates how to create a 'cycling' effect of different choices through clicking on them.

The cycle starts with the use of the [`<<include>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-include) macro and assumption of *\$choicesCount* beginning at the number -1. Within the passage "Cycling", the first 'cycle' begins with testing if the variable *\$choices* exists. If it does not, *\$choices* and *\$choicesCount* are set (created) to their initial values.

Next, *\$choicesCount* is then increased by one to the start value of 0 (the first location of an array in SugarCube) and the position of *\$choices* is shown based on this.

If the user clicks on the link (created through using the [`<<linkreplace>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-linkreplace) and `<<include>>` macros) again, future 'cycles' test if *\$choicesCount* increases beyond the number of values in the *\$choices* array and resets it to 0.

At the end of every cycle, the currently selected value is stored in the variable *\$cyclingResult* for future access and usage.

## Example

[Download](sugarcube_cycling_example.html)

## Twee Code

```twee
:: StoryTitle
Cycling Choices in SugarCube

:: Start
Click options to cycle: <<include "Cycling">>
[[Submit|Results]]

:: Cycling
<<silently>>
<<if not $choices>>
  <<set $choicesCount to -1>>
  <<set $choices to ["First", "Second", "Third"]>>
<</if>>

<<set $choicesCount to $choicesCount + 1>>

<<if $choicesCount >= $choices.length>>
   <<set $choicesCount to 0>>
<</if>>

<<set $cyclingResult to $choices[$choicesCount]>>
<</silently>>
\<<linkreplace $choices[$choicesCount]>><<include "Cycling">><</linkreplace>>

:: Results
$cyclingResult

```

[Twee Download](sugarcube_cycling_twee.txt)

## See Also

[Setting and Showing Variables](../../settingandshowing/sugarcube/sugarcube_settingandshowing.md), [Modularity](../../modularity/sugarcube/sugarcube_modularity.md)
