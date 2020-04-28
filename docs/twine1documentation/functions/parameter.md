# *parameter(number)*

This is an interesting one. Suppose you're `<<display>>`ing a passage using the shorthand, and you include some extra values at the end of the tag:

`<<CaramelCanoe "oars" "satchel">>`

With *parameter()*, you can access these extra values and use them inside the displayed passage:

```twee
::CaramelCanoe
You're canoeing down the caramel river, rowing with <<print parameter(0)>>, your <<print parameter(1)>> by your side.
```

Running the aforementioned `<<display>>` will show "You're canoeing down the caramel river, rowing with oars, your satchel by your side."

This allows you to subtly alter a passage depending on where and how it's `<<display>>`ed, without using variables. You can, for instance, make a passage that describes the character's clothes, and you can supply different adjectives to the passage, just by including them in the shorthand `<<display>>`.
