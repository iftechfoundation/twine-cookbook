# *either(value, value, ...)*

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

Give the *either()* function several string or number values, separated by commas, and it will pick one of them randomly. This allows a good degree of randomness to be inserted into the story, while still being fairly readable.

You can use *either()* with `<<print>>` to print a random message or phrase...

```twee
"I sentence you to be buried alive in <<print either("rhinoceros","buffalo","triceratops")>>
<<print either("vomit", "sweat", "snot")>>!" the JudgeBot crackles noisily.
```

You can also use *either()* with `<<set>>` to set variables to random values:

```twee
<<set $playerMoxie to either(2, 4, 6)>>
<<set $playerAttire to either("green", "black", "rainbow")>>
You have <<print $playerMoxie>> moxie points, and <<print $playerAttire>> armour.
```

And, in addition to macros, you can use *either()* with the link syntax to make a link that goes to a random passage:

```twee
You plunge into the [[glowing vortex|either("12000 BC","The Future","2AM Yesterday")]]
```
