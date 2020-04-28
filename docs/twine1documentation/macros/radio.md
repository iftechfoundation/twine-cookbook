# `<<radio>>`

The `<<radio>>` macro lets you offer your reader with a familiar radio button input. While a `<<checkbox>>` set lets the reader make multiple choices, radio buttons are mutually exclusive–your reader can choose only one option.

Note that, in order for the value to be stored, there must be a `<<button>>` in the passage, and the user must click it.

This code sample:

```twee
  Would you like to see some radio buttons?
  
  <<radio $choice "yes">>
  <<radio $choice "no">>
  <<radio $choice "maybe">>
  
  <<button [[Go on|go_on]]>>
```

In this example, the variable $choice is the name for this set of radio buttons. You can set this to any variable name you like.

You see each input has a value–in this example, "yes," "no," and "maybe."

These are what will be displayed to the reader AND stored in the variable (*$choice*) to be used in the next passage.

Thus if a reader chooses "maybe" and clicks the button "Go on," it's the same as telling Twine this:

```twee
<<set $choice = "maybe">>
```

Twine 1 forces a line break between radio buttons. To work around this, you can set your radio buttons in an HTML table:

```html
  <table>
      <tr>
          <td>Sound?</td><td><<radio $sound "yes">></td><td><<radio $sound "no">></td>
      </tr>
      <tr>
          <td>Color effects?</td><td><<radio $color_effects "yes">></td><td><<radio $color_effects "no">></td>
      </tr>
  </table>
  <<button [[Begin the Game|Begin]]>>
```

There is no native option to mark a radio button as selected before your reader makes their choice.

One option to work around this in Twine natively is to initialize your variable to the default value and offer the reader only the other choice(s):

```twee
  <<set $sound = "no">>\
  <<set $color_effects = "no">>
  <table>
      <tr>
          <td>Sound?</td><td></td><td><<radio $sound "yes">></td>
      </tr>
      <tr>
          <td>Color effects?</td><td></td><td><<radio $color_effects "yes">></td>
      </tr>
  </table>
  <<button [[Start the Game|start_game]]>>
```

A disadvantage of this approach is that, once the option is checked, it can't be unchecked back to whatever you set as the default.
