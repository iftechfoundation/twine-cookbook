# "Moving through a 'dungeon": Harlowe (v2.0)

## Summary

"Moving through a 'dungeon'" uses the <a href="https://twine2.neocities.org/#macro_a">(array:)</a> macro to create a multidimensional array. Movement positions are then tracked through X and Y variables for a grid system. Each movement subtracts or adds to its cooresponding X or Y position and is compared to those same positions within the array. Different directions are shown if movement is possible in that direction.

A map of the array is created by iterating through temporary variables and placing different symbols matching walls, movement spaces, and the player herself.

## Live Example

<section>
<iframe src="harlowe_dungeonmoving_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_dungeonmoving_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Harlowe: Moving through Dungeons


:: User Style [stylesheet]
tw-include[type="startup"], tw-hook[name="workarea"] {
	display: none;
}
tw-hook[name="map"] {
    font-family: monospace; 
	line-height: 1.75;
	font-size: 16pt;
}


:: Start
|map>[(display: "Map")]


:: Map
(set: $map to "")\
|workarea>[
	(for: each _y, ...(range: 1, $dungeon's length))[
		(for: each _x, ...(range: 1, $dungeon's (_y)'s length))[
			(if: _x is $positionX and _y is $positionY)[
				(set: $map to it + "P ")
			]
			(else-if: $dungeon's (_y)'s (_x) is 0)[
				(set: $map to it + "&num; ")
			]
			(else-if: $dungeon's (_y)'s (_x) is 1)[
				(set: $map to it + ". ")
			]
			(else-if: $dungeon's (_y)'s (_x) is 2)[
				(set: $map to it + "E ")
			]
		]
		(set: $map to it + " <br>")
	]
]\
$map

{
	(set: $seperator to "")\
	(set: _north to $dungeon's ($positionY - 1)'s ($positionX))
	(set: _east to $dungeon's ($positionY)'s ($positionX + 1))
	(set: _south to $dungeon's ($positionY + 1)'s ($positionX))
	(set: _west to $dungeon's ($positionY)'s ($positionX - 1))

	(if: _north is 1)[
		$seperator
		(link: "North")[
			(set: $positionY to it - 1)
			(replace: ?map)[(display: "Map")]
		]
		(set: $seperator to " | ")
	]
	(else-if: _north is 2)[
		$seperator[[Exit]]
		(set: $seperator to " | ")
	]

	(if: _east is 1)[
		$seperator
		(link: "East")[
			(set: $positionX to it + 1)
			(replace: ?map)[(display: "Map")]
		]
		(set: $seperator to " | ")
	]
	(else-if: _east is 2)[
		$seperator[[Exit]]
		(set: $seperator to " | ")
	]

	(if: _south is 1)[
		$seperator
		(link: "South")[
			(set: $positionY to it + 1)
			(replace: ?map)[(display: "Map")]
		]
		(set: $seperator to " | ")
	]
	(else-if: _south is 2)[
		$seperator[[Exit]]
		(set: $seperator to " | ")
	]

	(if: _west is 1)[
		$seperator
		(link: "West")[
			(set: $positionX to it - 1)
			(replace: ?map)[(display: "Map")]
		]
	]
	(else-if: _west is 2)[
		$seperator[[Exit]]
	]
}


:: Startup [startup]
{	
	(set: $dungeon to (array: 
			(a: 0,0,0,0,0,0,0,0,0,0,0),
			(a: 0,1,1,1,0,1,1,1,1,1,0),
			(a: 0,0,0,1,0,0,0,0,0,1,0),
			(a: 0,1,0,1,1,1,1,1,0,1,0),
			(a: 0,1,0,0,0,0,0,1,0,1,0),
			(a: 0,1,1,1,1,1,1,1,0,1,0),
			(a: 0,0,0,0,0,0,0,1,0,1,0),
			(a: 0,1,0,1,1,1,1,1,1,1,0),
			(a: 0,1,0,1,0,0,0,1,0,0,0),
			(a: 0,1,1,1,0,1,1,1,1,2,0),
			(a: 0,0,0,0,0,0,0,0,0,0,0)
		)
	)
    (set: $positionX to 2)
    (set: $positionY to 2)
}


:: Exit
You have exited the map.
```

Download: <a href="harlowe_dungeonmoving_twee.txt" target="_blank">Twee Code</a>

## See Also

[Setting and Showing Variables](../../settingandshowing/harlowe/harlowe_settingandshowing.md), 
[Conditional Statements](../../conditionalstatements/harlowe/harlowe_conditionalstatements.md), [Modularity](../../modularity/harlowe/harlowe_modularity.md)
