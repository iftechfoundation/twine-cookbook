# "Moving through a 'dungeon": Harlowe (v2.0)

## Summary

"Moving through a 'dungeon'" uses the <a href="https://twine2.neocities.org/#macro_a">(array:)</a> macro to create a multidimensional array. Movement positions are then tracked through X and Y variables for a grid system. Each movement subtracts or adds to its cooresponding X or Y position and is compared to those same positions within the array. Different directions are shown if movement is possible in that direction.

A map of the array is created through using temporary variables and building a HTML table by iterating through the it and placing different symbols matching walls, movement spaces, and the player herself.

## Live Example

<section>
<iframe src="harlowe_dungeonmoving_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_dungeonmoving_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Harlowe: Moving through Dungeons

:: Start
|map>[(display: "Map")]
|=
(link-repeat: "Up")[{
	(set: _row to $dungeon's ($positionX) )
	(if: _row's ($positionY - 1) is not 1)[
		(set: $positionY to it - 1)
	]
	(replace: ?map)[(display: "Map")]
}]
=|=
(link-repeat: "Left")[{
	(set: _row to $dungeon's ($positionX) )
	(if: _row's ($positionX - 1) is not 1)[
		(set: $positionX to it - 1)
	]
	(replace: ?map)[(display: "Map")]
}]
=|=
(link-repeat: "Right")[{
	(set: _row to $dungeon's ($positionX) )
	(if: _row's ($positionX + 1) is not 1)[
		(set: $positionX to it + 1)
	]
	(replace: ?map)[(display: "Map")]
}]
=|=
(link-repeat: "Down")[{
	(set: _row to $dungeon's ($positionX) )
	(if: _row's ($positionY + 1) is not 1)[
		(set: $positionY to it + 1)
	]
	(replace: ?map)[(display: "Map")]
}]

|==|

:: Map
{
	(set: $dungeonTable to "<table>")

	(set: $i to 0)
	
	(for: each _row, ...$dungeon) [
		
		(set: $i to it + 1)
		
		(set: $dungeonTable to it + "<tr>")
		
		(set: $j to 0)
		
		(for: each _col, ..._row) [
			
			(set: $j to it + 1)
			
			(if: $i is $positionY and $j is $positionX)[
				(set: $dungeonTable to it + "<td>P</td>")
			]
			(else:) [
				(if: _col is 0) [
					(set: $dungeonTable to it + "<td>.</td>")
				]
			]
			
			(if: _col is 1)[
				(set: $dungeonTable to it + "<td>#</td>")
			]
		]
		
		(set: $dungeonTable to it + "</tr>")
	]
	
	(set: $dungeonTable to it + "</table>")

	$dungeonTable
}

:: Startup[startup]
{	
	(set: $dungeon to (array: (a: 1,1,1,1,1),
							  (a: 1,0,0,0,1),
							  (a: 1,0,0,0,1),
							  (a: 1,0,0,0,1),
							  (a: 1,1,1,1,1) ) )
	(set: $positionX to 2)
	(set: $positionY to 2)
}
```

Download: <a href="harlowe_dungeonmoving_twee.txt" target="_blank">Twee Code</a>

## See Also

[Setting and Showing Variables](../../settingandshowing/harlowe/harlowe_settingandshowing.md), 
[Conditional Statements](../../conditionalstatements/harlowe/harlowe_conditionalstatements.md), [Modularity](../../modularity/harlowe/harlowe_modularity.md)
