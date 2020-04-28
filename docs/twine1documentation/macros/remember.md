# `<<remember>>`

Variables are reset every time the reader restarts a story. If you'd like to remember the value of a variable after the game, use the `<<remember>>` macro. It works exactly the same way as `<<set>>`, except it stores the variable in browser storage that remains between sessions.

```twee
At long last, you have escaped the dungeons. <<remember $escapes += 1>>

So far, you have escaped the dungeons <<print $escapes>> times.
```

If you are only interested in remembering the current state of a variable, you don't need to include an assignment:

`<<remember $meals>>`
