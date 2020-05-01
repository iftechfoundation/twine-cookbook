# *visited(string, string...)*

Has a value equal to the number of times you've visited the named passage. It's fairly useful - this can eliminate or greatly reduce the need to use "counter variables" to keep track of the player's actions. If the passage name is omitted, as in *visited()*, then its value is for the current passage.

If multiple strings are supplied to it, then it will return the value for the passage that was visited the least.

```twee
You've visited this passage <<print visited()>> times.

You've visited the Pond <<print visited("Pond")>> times.
```

Since visited() returns the value for the passage visited the least, then
if the below result is greater than 0 (i.e. not false), then both passages
must have been visited at least once.

```twee
<<if visited("Armoury", "Haberdasher")>>\
With your sword and hat, nothing can stop you!
<<endif>>\
```

**Advanced use:** if you want to display something on every third time you visit a passage (no matter if you visit it 3 times, 10 times, or 100 times), then you can use the modulo operator % to transform the number:

```twee
<<if visited() % 3 is 0>>\
"Every 3 visits to this passage, I walk the Earth again," croons Count Dracula.
<<endif>>\
```

Feel free to modify the "3" to any number you wish, to make something happen on every four visits, every ten visits, etc.
