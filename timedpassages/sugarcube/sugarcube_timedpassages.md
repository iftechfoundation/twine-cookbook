# "Timed Passages": SugarCube (v2.18)

## Summary

Made famous in [*Queers in Love at the End of the World* (2013)](http://auntiepixelante.com/endoftheworld/), "Timed Passages" uses the the [*&lt;&lt;repeat&gt;&gt;*](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-repeat) macro to repeat while checking if the timer has reached zero. If so, the [*&lt;&lt;goto&gt;&gt;*](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-goto) macro will immediately transition to another passage.

## Twee Code

```
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

## See Also

[Delayed Text](../../delayedtext/sugarcube/sugarcube_delayedtext.md), [Typewriter Effect](../../typewriter/sugarcube/sugarcube_typewriter.md)
