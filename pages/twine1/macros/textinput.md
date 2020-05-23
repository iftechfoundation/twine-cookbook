# `<<textinput>>`

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

The `<<textinput>>` macro creates a standard HTML text box that allows the player to enter text. The text will be set to a variable once a `<<button>>` macro is clicked.

## Usage

`<<textinput $variable>>`

When a button is clicked, the text entered into the textbox will be set into the variable. Clicking normal links will ignore the text. (This allows normal links to serve as a "cancel" or "go back" operation, allowing the player to navigate without unintentionally altering the variables.)

## Button shorthand

As mentioned, the inputted text is ignored by Twine unless a button is clicked, which acts as a way to "submit" the text into the given variable. There is a way to create a button without using an extra `<<button>>` macro. Simply add a link as an extra argument to the macro:

`<<textinput $variable [[link text|passage name]] >>`

This creates a button immediately after the text box, which functions accordingly.
