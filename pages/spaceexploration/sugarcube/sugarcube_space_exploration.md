# "Space Exploration": SugarCube (v2.18)

## Summary

Games in the [rogue-like genre](https://en.wikipedia.org/wiki/Roguelike) often have random events that influence player choices. Frequently, decisions can have lasting impact or even lead to an ending of play in that session or run depending on these random outcomes.

Heavily inspired by *[FTL: Faster Than Light](https://en.wikipedia.org/wiki/FTL:_Faster_Than_Light)* (2012), this example uses the **[random()](http://www.motoslave.net/sugarcube/2/docs/functions.html#random)** function to generate a system of planets consisting of either RED, more risk and more reward, or GREEN, less risk and less reward. Upon entering a system of planets, the player can choose to visit these planets for different outcomes based on a series of choices and an additional use of the **random()** function. While traveling, the player must also balance the health of the ship, the number of jumps left, and the current fuel that are all displayed using the [`<<include>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-include) macro. Finally, to capture the permanence of many roguelike games, the [`<<goto>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-goto) macro is used to prevent the use of the normal undo/redo in SugarCube.

To cleanly present the text, this example also uses both the [`<<silently>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-silently) macro, to disregard all output, and [`<<nobr>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-nobr) macro, to collapse the whitespace.

## Example

[Download](sugarcube_space_exploration_example.html){ target="_top" download="sugarcube_space_exploration_example.html"}

## Twee Code

```twee
:: StoryTitle
Space Exploration in SugarCube

:: Start
[[Explore Space|Explore Space 1]]

:: StoryInit
<<set $health to 20>>
<<set $fuel to 4>>
<<set $system to [] >>
<<set $numberOfJumpsLeft to 10>>

:: Explore Space 1
<<link "Hyperjump">>
  <<set $fuel to $fuel - 1>>
  <<set $numberOfJumpsLeft to $numberOfJumpsLeft - 1>>
  <<goto "Explore Space 2">>
<</link>>

<div id="HUD">
  <<include "HUD">>
</div>

<<include "Generate System">>
<<include "Display System">>

:: Explore Space 2
<<link "Hyperjump">>
  <<set $fuel to $fuel - 1>>
  <<set $numberOfJumpsLeft to $numberOfJumpsLeft - 1>>
  <<goto "Explore Space 1">>
<</link>>

<div id="HUD">
  <<include "HUD">>
</div>

<<include "Generate System">>
<<include "Display System">>

:: Generate System
<<silently>>
  <<set _planets to random(1, 4) >>

  <<set $system to new Array(_planets) >>

  <<for _i to 0; _i lt _planets; _i++>>
    <<set $system[_i] to either("RED", "GREEN") >>
  <</for>>

<</silently>>

:: Display System
<<nobr>>
  <<for _i to 0; _i lt $system.length; _i++>>
    <<if $system[_i] eq "RED">>
       <<linkreplace $system[_i]>>
         <<include "Show Outcome - Red">>
       <</linkreplace>>
    <</if>>
    <<if $system[_i] eq "GREEN">>
       <<linkreplace $system[_i]>>
         <<include "Show Outcome - Green">>
       <</linkreplace>>
    <</if>>
    <br>
  <</for>>
<</nobr>>

:: Show Outcome - Red
<<nobr>>
  <<set _percentage to random(1, 10) >>

  <<if _percentage gte 6>>

    <<set _foundHealth to random( 1, 5) >>
    <<set _foundFuel to random( 1, 3) >>

    The hostile environment damaged the ship, but extra fuel was found. (-_foundHealth to health and +_foundFuel to fuel)

    <<set $health to $health - _foundHealth >>
    <<set $fuel to $fuel + _foundFuel >>

  <<elseif _percentage lte 3>>

    <<set _foundHealth to random(2, 7) >>

    A hostile ship attacked. (-_foundHealth to health)

    <<set $health to $health - _foundHealth >>

  <<else>>
    Nothing happened.
  <</if>>

  <<replace "#HUD">>
    <<include "HUD">>
  <</replace>>

<</nobr>>

:: Show Outcome - Green
<<nobr>>
  <<set _percentage to random(1, 10)>>

  <<if _percentage eq 1>>

    <<set _foundFuel to random( 1, 2)>>

    Fuel was found in some wreckage. (+_foundFuel to fuel)

    <<set $fuel to $fuel + _foundFuel>>

  <<elseif _percentage gte 6>>

    <<set _foundHealth to random( 1, 3) >>

    During a brief pause, the ship was able to be repaired. (+_foundHealth to health)

    <<set $health to $health + _foundHealth>>

  <<else>>
    Nothing happened.
  <</if>>

  <<replace "#HUD">>
    <<include "HUD">>
  <</replace>>

<</nobr>>

:: HUD
Health: $health
Fuel: $fuel
Number of Jumps Left: $numberOfJumpsLeft
<<include "Check Status">>

:: Destroyed
The ship exploded in flight.

!!!Game Over.

:: Lost in space
Without fuel, the ship tumbled and spun in the endless black.

!!!Game Over

:: Safe
After 10 hyperjumps, the ship left the hazardous area and called for help.

!!!Success!

:: Check Status
<<nobr>>
  <<if $health lte 0>>
    <<goto "Destroyed">>
  <</if>>
  <<if $fuel lte 0>>
    <<goto "Lost in space">>
  <</if>>
  <<if $numberOfJumpsLeft lte 0>>
    <<goto "Safe">>
  <</if>>
<</nobr>>

```

[Twee Download](sugarcube_space_exploration_twee.txt){ target="_top" download="sugarcube_space_exploration_twee.txt"}
