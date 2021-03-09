# "Timed Passages": SugarCube (v2.18)

## Summary

Made famous in [*Queers in Love at the End of the World*](https://w.itch.io/end-of-the-world) (2013), "Timed Passages" uses the the [`<<repeat>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-repeat) macro to repeat while checking if the timer has reached zero. If so, the [`<<goto>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-goto) macro will immediately transition to another passage.

## Example

[Download](sugarcube_timedpassages_example.html){ target="_top" download="sugarcube_timedpassages_example.html"}

## Twee Code

```twee
:: StoryTitle
SugarCube: Timed Passages

:: StoryJavaScript[script]
UIBar.destroy();

:: Start
[[Start Timer|First Passage]]

:: Timer
<span id="countdown">The world will end in $seconds seconds.</span>
<<silently>>
    <<repeat 1s>>
        <<set $seconds to $seconds - 1>>
        <<if $seconds gt 0>>
            <<replace "#countdown">>The world will end in $seconds seconds.<</replace>>
        <<else>>
            <<replace "#countdown">><</replace>>
            <<goto "World End">>
            <<stop>>
        <</if>>
    <</repeat>>
<</silently>>

:: First Passage
<<include "Timer">>

[[Second Passage]]

:: Second Passage
<<include "Timer">>

[[First Passage]]

:: World End
The world has ended.

:: StoryInit
<<set $seconds to 10>>

```

[Twee Download](sugarcube_timedpassages_twee.txt){ target="_top" download="sugarcube_timedpassages_twee.txt"}

## See Also

[Delayed Text](../../delayedtext/sugarcube/sugarcube_delayedtext.md), [Typewriter Effect](../../typewriter/sugarcube/sugarcube_typewriter.md)
