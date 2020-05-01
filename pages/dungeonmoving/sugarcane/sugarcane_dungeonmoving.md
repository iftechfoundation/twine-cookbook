# "Moving through a 'dungeon'": Sugarcane (v2.0)

<div class="alertbox warning"><strong>Note:</strong> The following example is designed for Twine 1.4.2.</div>

## Summary

"Moving through a 'dungeon'" uses an array of arrays to track positions 'moved' through using X and Y variables. It also creates a `<<navigate>>` macro that handles the showing of directions.

## Live Example

<section>
<iframe src="sugarcane_dungeonmoving_example.html" height=400 width=90%></iframe>

Download: <a href="sugarcane_dungeonmoving_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```twee
:: North
<<set $posy = $posy - 1>>
<<navigate>>
<<if $North eq 1>>
[[North]]
<<endif>>
<<if $South eq 1>>
[[South]]
<<endif>>
<<if $West eq 1>>
[[West]]
<<endif>>
<<if $East eq 1>>
[[East]]
<<endif>>
<<if $Exit eq 1>>
[[Exit]]
<<endif>>


:: StoryTitle
Sugarcane: Moving through a 'Dungeon'


:: Start
<<display "Maze Addon">>

[[Enter Dungeon]]


:: Maze Addon
<<silently>>
<<set $MazeAddon =
function()
{
  
   var maze = [[0,0,0,0,0,0,0,0,0,0,0],
[0,1,1,1,0,1,1,1,1,1,0],
[0,0,0,1,0,0,0,0,0,1,0],
[0,1,0,1,1,1,1,1,0,1,0],
[0,1,0,0,0,0,0,1,0,1,0],
[0,1,1,1,1,1,1,1,0,1,0],
[0,0,0,0,0,0,0,1,0,1,0],
[0,1,0,1,1,1,1,1,1,1,0],
[0,1,0,1,0,0,0,1,0,0,0],
[0,1,1,1,0,1,1,1,1,2,0],
[0,0,0,0,0,0,0,0,0,0,0]];
   
  var x = 1;
  var y = 1;
  
  $posx = 1;
  $posy = 1;
  
  macros['navigate'] =
	{
		handler: function(obj, fnc, val)
		{
			x = $posx; y = $posy;
         if(maze[y-1][x] eq 1)
         { $North = 1; }
         else if(maze[x][y+1] eq 2) {$Exit = 1;}
         else {$North = 0;}
         
         if(maze[y+1][x] eq 1)
         { $South = 1; }
         else if(maze[x][y-1] eq 2) {$Exit = 1;}
         else {$South = 0;}
         
         if(maze[y][x-1] eq 1)
         { $West = 1; }
         else if(maze[x-1][y] eq 2) {$Exit = 1;}
         else {$West = 0;}
         
         if(maze[y][x+1] eq 1)
         { $East = 1; }
         else if(maze[x+1][y] eq 2) {$Exit = 1;}
         else {$East = 0;}
		}
	}
   
   
}
>>
<<print $MazeAddon()>>
<<endsilently>>


:: StoryAuthor
@videlais


:: West
<<set $posx = $posx - 1>>
<<navigate>>
<<if $North eq 1>>
[[North]]
<<endif>>
<<if $South eq 1>>
[[South]]
<<endif>>
<<if $West eq 1>>
[[West]]
<<endif>>
<<if $East eq 1>>
[[East]]
<<endif>>
<<if $Exit eq 1>>
[[Exit]]
<<endif>>


:: East
<<set $posx = $posx + 1>>
<<navigate>>
<<if $North eq 1>>
[[North]]
<<endif>>
<<if $South eq 1>>
[[South]]
<<endif>>
<<if $West eq 1>>
[[West]]
<<endif>>
<<if $East eq 1>>
[[East]]
<<endif>>
<<if $Exit eq 1>>
[[Exit]]
<<endif>>


:: Enter Dungeon
<<navigate>>
<<if $North eq true>>
[[North]]
<<endif>>
<<if $South eq true>>
[[South]]
<<endif>>
<<if $West eq true>>
[[West]]
<<endif>>
<<if $East eq true>>
[[East]]
<<endif>>


:: South
<<set $posy = $posy + 1>>
<<navigate>>
<<if $North eq 1>>
[[North]]
<<endif>>
<<if $South eq 1>>
[[South]]
<<endif>>
<<if $West eq 1>>
[[West]]
<<endif>>
<<if $East eq 1>>
[[East]]
<<endif>>
<<if $Exit eq 1>>
[[Exit]]
<<endif>>


:: Exit

```

Download: <a href="sugarcane_dungeonmoving_twee.txt" target="_blank">Twee Code</a>
