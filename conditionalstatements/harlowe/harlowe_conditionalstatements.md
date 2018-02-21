# "Conditional Statements": Harlowe (v2.0)

## Summary

The [*(if:)*](https://twine2.neocities.org/#macro_if) and [*(else:)*](https://twine2.neocities.org/#macro_else) macros conditionally produce commands that can be attached to hooks in Harlowe. If the statement is true, the *(if:)* section will be run. Otherwise, the *(else:)* section will be.

## Live Example

<section>
<iframe src="harlowe_conditionalstatements_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_conditionalstatements_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Conditional Statements in Harlowe

:: Start
(set: $animal to "horse")

(if: $animal is "dog")[It's a dog!]
(else:)[It's a horse!]
```

Download: <a href="harlowe_conditionalstatements_twee.txt" target="_blank">Twee Code</a>

