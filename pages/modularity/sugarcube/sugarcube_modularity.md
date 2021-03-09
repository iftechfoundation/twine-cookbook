# "Modularity": SugarCube (v2.18)

## Summary

In programming terminology, modularity refers to dividing software into different sections related to their purpose or to better organize the whole. In SugarCube, this technique can be used through the [`<<include>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-include) macro to print the contents of one passage in another. Parts of a story can often be re-used in this way.

The[`<<widget>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-widget) macro offers a simplified way of creating new, custom macros using other SugarCube macros and TwineScript instead of JavaScript. When compared to `<<include>>`, widgets have the advantage of accepting arguments and expressions similar to the way other SugarCube macros can. New widgets must be added through passages with the tag `widget`.

## Example

[Download](sugarcube_modularity_example.html){ target="_top" download="sugarcube_modularity_example.html"}

## Twee Code

```twee
:: StoryTitle
Modularity in SugarCube

:: Start
<<set $lineOne to "Give us a verse">>
<<set $lineTwo to "Drop some knowledge">>

<<include "showLineOne">>
<<include "showLineTwo">>

<<showLine 1>>
<<showLine 2>>

:: showLineWidget [widget]
<<widget 'showLine'>>\
    <<nobr>>
        <<if $args[0] is 1>>
            $lineOne
        <<elseif $args[0] is 2>>
            $lineTwo
        <</if>>
    <</nobr>>\
<</widget>>

:: showLineOne
$lineOne

:: showLineTwo
$lineTwo
```

[Twee Download](sugarcube_modularity_twee.txt){ target="_top" download="sugarcube_modularity_twee.txt"}
