# "Timed Passages": SugarCube (v2.18)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary
Made famous in <a href="http://auntiepixelante.com/endoftheworld/">Queers in Love at the End of the World</a>, "Timed Passages" uses the the *&lt;&lt;repeat&gt;&gt;* macro to repeat while checking if the timer has reached zero. If so, the *&lt;&lt;goto&gt;&gt;* macro will immediately transition to another passage.

## Live Example
<section>
<iframe src="sugarcube_timedpassages_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_timedpassages_example.html" target="_blank">Live Example</a>
</section>

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

Download: <a href="sugarcube_timedpassages_twee.txt" target="_blank">Twee Code</a>
