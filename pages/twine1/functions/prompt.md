# *prompt(string, string)*

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

Displays a text input dialog box. The text entered here will be the value of the function. The first string you give it is the message to display to the player. The second is the default value for the text input. This is a browser built-in.

```twee
<<set $name to prompt("What's your name?","Alyssa P. Hacker")>>
As an alternative to a browser dialog box, you can instead use the <<textinput>> macro.
```
