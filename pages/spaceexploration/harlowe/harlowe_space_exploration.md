# "Space Exploration": Harlowe (v2.0)

## Summary

Games in the [rogue-like genre](https://en.wikipedia.org/wiki/Roguelike) often have random events that influence player choices. Frequently, decisions can have lasting impact or even lead to an ending of play in that session or run depending on these random outcomes.

Heavily inspired by [*FTL: Faster Than Light*](https://en.wikipedia.org/wiki/FTL:_Faster_Than_Light) (2012), this example uses the [`(random:)`](https://twine2.neocities.org/#macro_random) macro to generate a system of planets consisting of either RED, more risk and more reward, or GREEN, less risk and less reward. Upon entering a system of planets, the player can choose to visit these planets for different outcomes based on a series of choices and an additional use of the (random:) macro. While traveling, the player must also balance the health of the ship, the number of jumps left, and the current fuel that are all displayed using the [`(display:)`](https://twine2.neocities.org/#macro_display) macro. Finally, to capture the permanence of many rogue-like games, the [`(go-to:)`](https://twine2.neocities.org/#macro_go-to) macro is used to prevent the use of the normal undo/redo operations in Harlowe.

## Example

[Download](harlowe_space_exploration_example.html){ target="_top" download="harlowe_space_exploration_example.html"}

## Twee Code

```twee
:: StoryTitle
Space Exploration in Harlowe

:: Start
[[Explore Space!|Explore Space 1]]

:: Startup[startup]
(set: $health to 20)
(set: $fuel to 3)
(set: $system to (a:) )
(set: $numberOfJumpsLeft to 10)

:: Generate System
{
  <!-- Save a range from 0 to a max of 3 (total of max 4) -->
  (set: _planets to (range: 0, (random: 1, 3) ) )

  <!-- Reset system -->
  (set: $system to (a:) )

  <!-- Create a new system based on the previous random range -->
  (for: each _i, ..._planets )[
    <!-- Add to the new system, setting either RED or GREEN planets -->
    (set: $system to it + (a: (either: "RED", "GREEN") ) )
  ]
 }

:: HUD
Health: $health
Fuel: $fuel
Number of Jumps Left: $numberOfJumpsLeft
(display: "Check Status")

:: Display System
{
  (for: each _planet, ...$system)[
    (if: _planet is "RED")[
      (link: _planet)[
        (display: "Show Outcome - Red")
      ]
    ]
    (if: _planet is "GREEN")[
      (link: _planet)[
        (display: "Show Outcome - Green")
      ]
    ]
    <br>
  ]
}

:: Explore Space 1
(link: "Hyperjump")[
  (set: $fuel to it - 1)
  (set: $numberOfJumpsLeft to it - 1)
  (goto: "Explore Space 2")
]
[(display: "HUD")]<HUD|
(display: "Generate System")
(display: "Display System")

:: Show Outcome - Green
{
  (set: _percentage to (random: 1, 10) )

  (if: _percentage is 1)[

    (set: _foundFuel to (random: 1, 2) )

    Fuel was found in some wreckage. (+_foundFuel to fuel)
    (set: $fuel to it + _foundFuel)

  ] (else-if: _percentage is >= 6)[

    (set: _foundHealth to (random: 1, 3) )

    During a brief pause, the ship was able to be repaired. (+_foundHealth to health)

    (set: $health to it + _foundHealth )

  ] (else:) [
    Nothing happened.
  ]

  (replace: ?HUD)[(display: "HUD")]
}

:: Show Outcome - Red
{
  (set: _percentage to (random: 1, 10) )

  (if: _percentage is >= 6)[

    (set: _foundHealth to (random: 1, 5) )
    (set: _foundFuel to (random: 1, 3) )

    The hostile environment damaged the ship, but extra fuel was found. (-_foundHealth to health and +_foundFuel to fuel)

    (set: $health to it - _foundHealth )
    (set: $fuel to it + _foundFuel )

  ] (else-if: _percentage <= 3)[

    (set: _foundHealth to (random: 2, 7) )

    A hostile ship attacked. (-_foundHealth to health)

    (set: $health to it - _foundHealth )

  ] (else:)[
    Nothing happened.
  ]

  (replace: ?HUD)[(display: "HUD")]
}

:: Explore Space 2
(link: "Hyperjump")[
  (set: $fuel to it - 1)
  (set: $numberOfJumpsLeft to it - 1)
  (goto: "Explore Space 1")
]
[(display: "HUD")]<HUD|
(display: "Generate System")
(display: "Display System")

:: Check Status
{
  (if: $health <= 0)[
    (goto: "Destroyed")
  ]
  (if: $fuel <= 0)[
    (goto: "Lost in space")
  ]
  (if: $numberOfJumpsLeft <= 0)[
    (goto: "Safe")
  ]

}

:: Destroyed
The ship exploded in flight.

###Game Over.

:: Lost in space
Without fuel, the ship tumbled and spun in the endless black.

###Game Over

:: Safe
After 10 hyperjumps, the ship left the hazardous area and called for help.

###Success!

```

[Twee Download](harlowe_space_exploration_twee.txt){ target="_top" download="harlowe_space_exploration_twee.txt"}
