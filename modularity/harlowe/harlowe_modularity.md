# "Modularity": Harlowe (v2.0)

## Summary

In programming terminology, modularity refers to dividing software into different sections related to their purpose or to better organize the whole. In Harlowe, this technique can be used through the [*(display:)*](https://twine2.neocities.org/#macro_display) macro to print the contents of one passage in another. Parts of a story can often be re-used in this way.

## Twee Code

```
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
