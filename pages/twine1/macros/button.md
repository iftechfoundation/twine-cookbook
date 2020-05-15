# `<<button>>`

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

The `<<button>>` macro creates a button, a special type of link that, when clicked, sets the data entered into other form macros in the passage ( `<<textinput>>`, `<<radio>>`, `<<checkbox>>`), and moves to another passage.

## Usage

The `<<button>>` macro should be provided with the familiar link syntax:

`<<button [[displayed text|passage name]]>>`

The resulting button behaves identically to a normal link, but, when clicked, additionally causes the data entered into `<<textinput>>`, `<<radio>>` and `<<checkbox>>` macros to be placed in the variables.

For instance, if the macro `<<textinput $FoodName>>` appears in the same passage with a `<<button>>`, and the text "pretzels" has been entered into the input box, then clicking the button will, in addition to changing passages, run the equivalent of `<<set $FoodName to "pretzels">>`.
