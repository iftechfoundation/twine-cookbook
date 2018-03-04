# "Moving through a 'dungeon'": SugarCube (v2.0)

## Summary

"Moving through a 'dungeon'" uses a two-dimensional array for the "map" and two variables, X and Y, to track movement through the space. The 'Map System' passage checks the positions of X and Y relative to the "map" and writes the available directional movement options. Once a direction is clicked, the X and Y values are added or subtracted corresponding to the direction and the map is re-drawn again. Symbols are then placed on the map matching the walls, movement space, and player.


## Live Example

<section>
<iframe src="sugarcube_dungeonmoving_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_dungeonmoving_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
SugarCube: Moving through a Dungeon

:: UserStylesheet[stylesheet]
#map {
    font-family: monospace; 
}

:: StoryInit
<<set $mapArray to 
[[0,0,0,0,0,0,0,0,0,0,0],
[0,1,1,1,0,1,1,1,1,1,0],
[0,0,0,1,0,0,0,0,0,1,0],
[0,1,0,1,1,1,1,1,0,1,0],
[0,1,0,0,0,0,0,1,0,1,0],
[0,1,1,1,1,1,1,1,0,1,0],
[0,0,0,0,0,0,0,1,0,1,0],
[0,1,0,1,1,1,1,1,1,1,0],
[0,1,0,1,0,0,0,1,0,0,0],
[0,1,1,1,0,1,1,1,1,2,0],
[0,0,0,0,0,0,0,0,0,0,0]]>>

<<set $positionX to 1>>
<<set $positionY to 1>>

:: Location
<span id="map">
<<nobr>>
<<for $i to 0; $i lt $mapArray.length; $i++>>
    <<for $k to 0; $k lt $mapArray[$i].length; $k++>>
        <<if $k eq $positionX and $i eq $positionY>>
            <<print "P">> 
        <<elseif $mapArray[$i][$k] eq 1>>
            <<print ".">> 
        <<elseif $mapArray[$i][$k] eq 0>>
            <<print "#">> 
        <<elseif $mapArray[$i][$k] eq 2>>
            <<print "E">> 
        <</if>>
    <</for>>
    <<print "<br>">>
<</for>>
<</nobr>>
</span>

:: East
<<set $positionX += 1>>
<<include "Map System">>

:: West
<<set $positionX -= 1>>
<<include "Map System">>

:: South
<<set $positionY += 1>>
<<include "Map System">>

:: North
<<set $positionY -= 1>>
<<include "Map System">>

:: Map System
<<include "Location">>
<<nobr>>
<<if $mapArray[$positionY-1][$positionX] eq 1>>
[[North]] | 
<<elseif $mapArray[$positionY-1][$positionX] eq 2>>
[[Exit]] | 
<</if>>
<<if $mapArray[$positionY][$positionX+1] eq 1>>
[[East]] | 
<<elseif $mapArray[$positionY][$positionX+1] eq 2>>
[[Exit]] | 
<</if>>
<<if $mapArray[$positionY+1][$positionX] eq 1>>
[[South]] | 
<<elseif $mapArray[$positionY+1][$positionX] eq 2>>
[[Exit]] | 
<</if>>
<<if $mapArray[$positionY][$positionX-1] eq 1>>
[[West]] | 
<<elseif $mapArray[$positionY][$positionX-1] eq 2>>
[[Exit]] | 
<</if>>
<</nobr>>

:: Exit
Double-click this passage to edit it.

```
Download: <a href="sugarcube_dungeonmoving_twee.txt" target="_blank">Twee Code</a>

## See Also

[Setting and Showing Variables](../../settingandshowing/sugarcube/sugarcube_settingandshowing.md), 
[Conditional Statements](../../conditionalstatements/sugarcube/sugarcube_conditionalstatements.md), [Modularity](../../modularity/sugarcube/sugarcube_modularity.md)
