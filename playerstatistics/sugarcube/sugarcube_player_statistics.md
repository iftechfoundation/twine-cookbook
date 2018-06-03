# "Player Statistics": SugarCube (v2.18)

## Summary

One of the most popular mechanics of table-top role-playing games are those where the player must determine their in-game statistics and then use them to make decsions.

In this example, the [&lt;&lt;link&gt;&gt;](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-link) macro is used multiple times to [replace content](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-replace) and [adjust values](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-set) based on [if](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-if) they are greater than a target number. In a second passage, these values are used in combination with a [random number](http://www.motoslave.net/sugarcube/2/docs/functions.html#random) between 1 to 6, mimicking a common 1d6 mechanic to check if a value is above a target number. 

## Live Example

<section>
<iframe src="sugarcube_player_statistics_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_player_statistics_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Player Statistics in SugarCube

:: Start
Empathy: \
<<link "[+]">>
	<<if $totalPoints gt 0>>
	  <<set $empathy++>>
	  <<set $totalPoints-->>
	  <<replace "#empathyStat">><<print $empathy>><</replace>>
	  <<replace "#pointsStat">><<print $totalPoints>><</replace>>
	<</if>>
<</link>>\ 
<<link "[-]">>
	<<if $empathy gt 0>>
	  <<set $empathy-->>
	  <<set $totalPoints++>>
	  <<replace "#empathyStat">><<print $empathy>><</replace>>
	  <<replace "#pointsStat">><<print $totalPoints>><</replace>>
	<</if>>
<</link>>
Intelligence: \
<<link "[+]">>
	<<if $totalPoints gt 0>>
	  <<set $intelligence++>>
	  <<set $totalPoints-->>
	  <<replace "#intelligenceStat">><<print $intelligence>><</replace>>
	  <<replace "#pointsStat">><<print $totalPoints>><</replace>>
	<</if>>
<</link>>\ 
<<link "[-]">>
	<<if $intelligence gt 0>>
	  <<set $intelligence-->>
	  <<set $totalPoints++>>
	  <<replace "#intelligenceStat">><<print $intelligence>><</replace>>
	  <<replace "#pointsStat">><<print $totalPoints>><</replace>>
	<</if>>
<</link>>
<<link "[Reset Points]">>
	<<set $empathy to 10>>
	<<set $intelligence to 10>>
	<<set $totalPoints to 5>>
	<<replace "#empathyStat">><<print $empathy>><</replace>>
	<<replace "#intelligenceStat">><<print $intelligence>><</replace>>
	<<replace "#pointsStat">><<print $totalPoints>><</replace>>
<</link>>

Empathy: <span id="empathyStat">10</span>
Intelligence: <span id="intelligenceStat">10</span>
Remaining Points: <span id="pointsStat">5</span>

[[Test Stats]]

:: StoryInit
<<set $empathy to 10>>
<<set $intelligence to 10>>
<<set $totalPoints to 5>>

:: Test Stats
<<linkreplace "Make an intelligence check?">>
	<<set _result to random(1, 6) + $intelligence >>
	<<if _result gte 15>>
	Intelligence Success! (_result >= 15)
	<<else>>
	Intelligence Failure! (_result < 15)
	<</if>>
<</linkreplace>>
<<linkreplace "Make an empathy check?">>
	<<set _result to random(1, 6) + $empathy >>
	<<if _result gte 15>>
	Emaphy Success! (_result >= 15)
	<<else>>
	Empathy Failure! (_result < 15)
	<</if>>
<</linkreplace>>

```

Download: <a href="sugarcube_player_statistics_twee.txt" target="_blank">Twee Code</a>

## See Also

[Conditional Statements](../../conditionalstatements/sugarcube/sugarcube_conditionalstatements.md), [Setting and Showing](../../settingandshowing/sugarcube/sugarcube_settingandshowing.md)
