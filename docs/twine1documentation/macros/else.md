# `<<else>>`

`<<else>>` is a macro that is used to indicate text that should be displayed if the condition is false. It is paired with `<<if>>` or `<<endif>>`.

```twee
The door to the left leads to the pantry.
<<if visited("Pantry")>>
No way are you going back in there!
<<else>>
Sounds like a good place to search...
<<endif>>
```

The `<<else>>` macro can itself contain another "if condition", which causes the contents to only display if THAT condition is true:

```twee
<<if $health is 3>>\
You're in tip-top condition - fighting fit and frankly fearsome. No human or god can lick you!
<<else if $health is 2>>\
DOOMED! You're DOOMED, puny player!! You've lost already! YOU CANNOT WIN!! MWAHAHAHAHA!
<<endif>>\
```

You can insert as many `<<else if>>`'s as you want inside an `<<if>>` / `<<endif>>` pair.

(**Note:** if you prefer, you can also write "else if" as "elseif".)
