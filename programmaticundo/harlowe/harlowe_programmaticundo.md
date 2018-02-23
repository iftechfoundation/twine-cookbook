# "Programmatic Undo": Harlowe (v2.0)

## Summary

While Harlowe supports allowing the user to undo and redo moves, the "undo" operation can also be accessed through the [*(undo:)*](https://twine2.neocities.org/#macro_undo) macro. Through its use, changes from the most current action can be "undone."

## Live Example

<section>
<iframe src="harlowe_programmaticundo_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_programmaticundo_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Programmatic Undo in Harlowe

:: Start
[[Enter the darkness]]

:: Enter the darkness
(link: "You are not ready. Go back!")[(undo:)]
```

Download: <a href="harlowe_programmaticundo_twee.txt" target="_blank">Twee Code</a>

