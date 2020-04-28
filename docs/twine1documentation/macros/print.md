# `<<print>>`

The `<<print>>` macro lets you print expressions, pure and simple.

Usage:

`<<print expression>>`

The expression's value is calculated and printed into the passage. If an error occurred while calculating, an error message will be printed instead.

## Basic examples

```twee
"So, <<print $playerName>>, we meet again!" booms the Wrestlemaster.
Alas! <<print visited()>> time(s) you've fallen in this damned pit!
```

## Changing values while printing them

The `<<print>>` macro has an extra feature: if you use "to", "+=", or other operators common to the `<<set>>` macro in the `<<print>>`'s expression, then it will change the variables and print the new values.

**For example:**

```twee
After the transfusion, you have <<set $blood -= 7>><<print $blood>> litres of blood left.
```

can be potentially rewritten as:

```twee
After the transfusion, you have <<print $blood -= 7>> litres of blood left.
```

## Shorthand form

You may find yourself frequently using «print» to simply print a variable, without alteration. `<<print>>` has a convenient shorthand form for this single case: you simply omit the word "print", leaving just the variable within the angle brackets. For instance, `<<print $beers>>` can become simply `<<$beers>>`.

This allows you to write Twine stories in a "template" style:

```twee
Your superior officer approaches. "<<$name>>, you've done a fine job. No, a superlative job. <<$species>> like you have no place on this cruel Earth, that rewards only greed and selfishness."
```

**Note:** you can only perform this shorthand form using variables! You cannot, for instance, write `<<visited()>>`.
