# "Saving Games": Harlowe (v2.0)

## Summary

Harlowe provides macros like [`(save-game:)`](https://twine2.neocities.org/#macro_save-game) and [`(load-game:)`](https://twine2.neocities.org/#macro_load-game) to store and retrieve game "saves" of the variables and current passage. [`(saved-games:)`](https://twine2.neocities.org/#macro_saved-games) can also be used to check if a certain game save exists.

Game saves are stored as cookies in the user's browser. If cookies cannot be stored for some reason, game saves will fail. It is recommended to always check if the game save was stored before trying to retrieve it later.

## Example

[Download](harlowe_savinggames_example.html){: target="_top" download="harlowe_savinggames_example.html"}

## Twee Code

```twee
:: StoryTitle
Saving Games in Harlowe

:: Start
(link:"Save game?")[
  (if:(save-game:"Slot A"))[
  (if: (saved-games:) contains "Slot A")[
    Slot A is in the saved-games datamap!
  ]
  (link: "Load Slot A?" )[
      (load-game: "Slot A")
  ]
  ](else: )[
    Sorry, I couldn't save your game.
  ]
]
```

[Twee Download](harlowe_savinggames_twee.txt){ target="_top" download="harlowe_savinggames_twee.txt"}
