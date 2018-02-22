# "Modularity": SugarCube (v2.18)

## Summary

In programming terminology, modularity refers to dividing software into different sections related to their purpose or to better organize the whole. In SugarCube, this technique can be used through the [*&lt;&lt;include&gt;&gt;*](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-include) macro to print the contents of one passage in another. Parts of a story can often be re-used in this way.

## Live Example

<section>
<iframe src="sugarcube_modularity_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_modularity_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Modularity in SugarCube

:: Start
<<set $lineOne to "Give us a verse">>
<<set $lineTwo to "Drop some knowledge">>

<<include "showLineOne">>
<<include "showLineTwo">>

:: showLineOne
$lineOne

:: showLineTwo
$lineTwo
```

Download: <a href="sugarcube_modularity_twee.txt" target="_blank">Twee Code</a>

