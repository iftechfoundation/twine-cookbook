# "Typewriter Effect": SugarCube (v2.32)

## Summary

SugarCube (versions ≥ 2.32.0) includes a [`<<type>>` macro](http://www.motoslave.net/sugarcube/2/docs/#macros-macro-type) for creating a typing effect for displayed text. Almost any type of content can be typed using this macro, including links, styling markup, and other macros that display text. 

## Example

[Download](sugarcube_typewriter_example.html)

## Twee Code

```twee
:: StoryTitle
Typewriter Effect in Sugarcube

:: Start
<<type 60ms>>\
Hello world!

<<link "Click here!">><</link>>
\<</type>>
```

[Twee Download](sugarcube_typewriter_twee.txt)

## See Also

[Delayed Text](../../delayedtext/sugarcube/sugarcube_delayedtext.md)
