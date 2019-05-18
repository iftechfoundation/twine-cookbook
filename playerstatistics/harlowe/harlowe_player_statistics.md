# "Player Statistics": Harlowe (v2.0)

## Summary

One of the most popular mechanics of table-top role-playing games are those where the player must determine their in-game statistics and then use them to make decisions.

In this example, the [(link-repeat:)](https://twine2.neocities.org/#macro_link-repeat) macro is used multiple times to [replace content](https://twine2.neocities.org/#macro_replace) and [adjust values](https://twine2.neocities.org/#macro_set) based on [if](https://twine2.neocities.org/#macro_if) they are higher than a target value. In a second passage, these values are used in combination with a [random number](https://twine2.neocities.org/#macro_random) between 1 to 6, mimicking a common 1d6 mechanic to check if a value is above a target number.

## Live Example

<section>
<iframe src="harlowe_player_statistics_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_player_statistics_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Player Statistics in Harlowe

:: Start
Empathy: {
  (link-repeat: "|+|")[
	  (if: $totalPoints > 0)[
		(set: $empathy to it + 1)
		(set: $totalPoints to it - 1)
		(replace: ?empathyStat)[|empathyStat>[$empathy]]
		(replace: ?pointsStat)[|pointsStat>[$totalPoints]]
	  ]
  ]

  (link-repeat: "|-|")[
	  (if: $empathy > 0)[
		(set: $empathy to it - 1)
		(set: $totalPoints to it + 1)
		(replace: ?empathyStat)[|empathyStat>[$empathy]]
		(replace: ?pointsStat)[|pointsStat>[$totalPoints]]
	  ]
  ]
}
Intelligence: {
  (link-repeat: "|+|")[
	  (if: $totalPoints > 0)[
		(set: $intelligence to it + 1)
		(set: $totalPoints to it - 1)
		(replace: ?intelligenceStat)[|intelligenceStat>[$intelligence]]
		(replace: ?pointsStat)[|pointsStat>[$totalPoints]]
	  ]
  ]

  (link-repeat: "|-|")[
	  (if: $intelligence > 0)[
		(set: $intelligence to it - 1)
		(set: $totalPoints to it + 1)
		(replace: ?intelligenceStat)[|intelligenceStat>[$intelligence]]
		(replace: ?pointsStat)[|pointsStat>[$totalPoints]]
	  ]
  ]
}
{
  (link-repeat: "|Reset Points|")[
	  (set: $empathy to 10)
	  (set: $intelligence to 10)
	  (set: $totalPoints to 5)
	  (replace: ?empathyStat)[|empathyStat>[$empathy]]
	  (replace: ?intelligenceStat)[|intelligenceStat>[$intelligence]]
	  (replace: ?pointsStat)[|pointsStat>[$totalPoints]]
  ]
}

Empathy: |empathyStat>[10]
Intelligence: |intelligenceStat>[10]
Remaining Points: |pointsStat>[5]

[[Test Stats]]

:: Test Stats
(link: "Make an intelligence check?")[
	(set: _result to (random: 1, 6) + $intelligence)
	(if: _result >= 15)[
	Intelligence Success! (_result >= 15)
	](else:)[
	Intelligence Failure! (_result < 15)
	]
]
(link: "Make an empathy check?")[
	(set: _result to (random: 1, 6) + $empathy)
	(if: _result >= 15)[
	Empathy Success! (_result >= 15)
	](else:)[
	Empathy Failure! (_result < 15)
	]
]

:: Startup[startup]
(set: $empathy to 10)
(set: $intelligence to 10)
(set: $totalPoints to 5)

```

Download: <a href="harlowe_player_statistics_twee.txt" target="_blank">Twee Code</a>

## See Also

[Conditional Statements](../../conditionalstatements/harlowe/harlowe_conditionalstatements.md), [Setting and Showing](../../settingandshowing/harlowe/harlowe_settingandshowing.md)
