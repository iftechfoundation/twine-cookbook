# *random(value, value)*

When given two positive numbers, this produces a positive whole number randomly selected between the two, inclusive. This function can (and should only) be used to generate random numbers within a wide range - such as 1 to 100.

Prior to version 1.4.2, you had to use the cumbersome `Math.random(value)*value` idiom to do this, which wasn't that memorable or succinct.

```twee
You have a <<print random(1,99)>> percent chance of complete and utter defeat!
```
