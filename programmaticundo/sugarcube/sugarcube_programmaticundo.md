# "Programmatic Undo": SugarCube (v2.18)

## Summary

While SugarCube supports allowing the user to undo and redo moves, the "undo" operation can also be accessed through the [`<<back>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-back) macro. Through its use, changes from the most current action can be "undone."

## Live Example

<section>
<iframe src="sugarcube_programmaticundo_example.html" height=400 width=90%></iframe>

Download: <a href="sugarcube_programmaticundo_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Programmatic Undo in SugarCube

:: Start
[[Enter the Darkness]]

:: Enter the Darkness
<<back "You are not ready! Go back!">>
```

Download: <a href="sugarcube_programmaticundo_twee.txt" target="_blank">Twee Code</a>

