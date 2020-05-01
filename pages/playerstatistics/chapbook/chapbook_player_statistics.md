# "Player Statistics": Chapbook (v1.0.0)

## Summary

One of the most popular mechanics of table-top role-playing games are those where the player must determine their in-game statistics and then use them to make decisions.

In Chapbook, the values of variables can only be changed as part of the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) or using [JavaScript](https://klembot.github.io/chapbook/guide/advanced/using-javascript-in-passages.html). This example combines the two and uses the [`{embed passage}`](https://klembot.github.io/chapbook/guide/references/modifiers.html) modifier to use different passages as sections of code and adjust values based on user interactions.

## Live Example

<section>
<iframe src="chapbook_player_statistics_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_player_statistics_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```twee
:: StoryTitle
Chapbook: Player Statistics

:: Start
{embed passage: "Setup"}
{embed passage: "Statistics"}

:: IncreaseEmpathy
empathy: empathy + 1
points: points - 1
--
{embed passage: "Statistics"}

:: DecreaseEmpathy
empathy: empathy - 1
points: points + 1
--
{embed passage: "Statistics"}

:: IncreaseIntelligence
intelligence: intelligence + 1
points: points - 1
--
{embed passage: "Statistics"}

:: DecreaseIntelligence
intelligence: intelligence - 1
points: points + 1
--
{embed passage: "Statistics"}

:: Setup
empathy: 10
intelligence: 10
points: 5
--

:: Statistics
{embed passage: "CheckValues"}

[if points > 0 && empathy > 0]
Empathy:
[[[+]->IncreaseEmpathy]] [[[-]->DecreaseEmpathy]]
[continued]

[if points > 0 && intelligence > 0]
Intelligence:
[[[+]->IncreaseIntelligence]] [[[-]->DecreaseIntelligence]]
[continued]

Empathy: {empathy}

Intelligence: {intelligence}

Remaining Points: {points}

[[Reset Points->Start]]

:: CheckValues
[JavaScript]
	let empathy = engine.state.get('empathy');
	let intelligence = engine.state.get('intelligence');
	let points = engine.state.get('points');
	
	if(empathy > 20){empathy = 20;}
	if(intelligence > 20){intelligence = 20;}
	if(points < 0){points = 0;}
	if(points > 25){points = 25;}
	
	engine.state.set('empathy', empathy);
	engine.state.set('intelligence', intelligence);
	engine.state.set('points', points);


```

Download: <a href="chapbook_player_statistics_twee.txt" target="_blank">Twee Code</a>
