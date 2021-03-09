# "Typewriter Effect": SugarCube (v2.18)

## Summary

"Typewriter Effect" demonstrates how to create a delayed character-by-character effect. In SugarCube, a [`<<widget>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-widget) macro named "typewriter" is created that uses the [`<<repeat>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-repeat) and `<<stop>>` macros internally to show one character every one second.

## Example

[Download](sugarcube_typewriter_example.html){: target="_top" download="sugarcube_typewriter_example.html"}

## Twee Code

```twee
:: StoryTitle
Typewriter Effect in Sugarcube

:: Start
<<typewriter "Hello, world">>

:: Typewriter[widget]
\<<widget typewriter>>
\  <!-- Create a SPAN with an ID -->
\  <span id="typewriter"></span>
\  <!-- In SugarCube, arrays start at 0 -->
\  <<set _textArrayLength to 0>>
\  <!-- Repeat every second -->
\  <<repeat 1s>>
\    <!-- Test if textArrayLength is greater than length of $args[0] -->
\    <<if _textArrayLength gte $args[0].length>>
\    <<stop>>
\    <<else>>
\    <!-- Append the current position to the existing characters -->
\    <<append "#typewriter">>$args[0][_textArrayLength]<</append>>
\    <!-- Update the length -->
\    <<set _textArrayLength++>>
\    <</if>>
\   <</repeat>>
\<</widget>>

```

[Twee Download](sugarcube_typewriter_twee.txt){ target="_top" download="sugarcube_typewriter_twee.txt"}

## See Also

[Delayed Text](../../delayedtext/sugarcube/sugarcube_delayedtext.md)
