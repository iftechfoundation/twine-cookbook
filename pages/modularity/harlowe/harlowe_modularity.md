# "Modularity": Harlowe (v2.0)

## Summary

In programming terminology, modularity refers to dividing software into different sections related to their purpose or to better organize the whole. In Harlowe, this technique can be used through the [`(display:)`](https://twine2.neocities.org/#macro_display) macro to print the contents of one passage in another. Parts of a story can often be re-used in this way.

## Live Example

<section>
<iframe src="harlowe_modularity_example.html" height=400 width=90%></iframe>

Download: <a href="harlowe_modularity_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```twee
:: StoryTitle
Modularity in Harlowe

:: Start
(set: $lineOne to "Give us a verse")
(set: $lineTwo to "Drop some knowledge")

(display: "showLineOne")
(display: "showLineTwo")

:: showLineOne
$lineOne

:: showLineTwo
$lineTwo
```

Download: <a href="harlowe_modularity_twee.txt" target="_blank">Twee Code</a>
