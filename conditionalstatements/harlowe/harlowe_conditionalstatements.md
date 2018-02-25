# "Conditional Statements": Harlowe (v2.0)

## Summary

The [*(if:)*](https://twine2.neocities.org/#macro_if) and [*(else:)*](https://twine2.neocities.org/#macro_else) macros conditionally produce commands that can be attached to hooks in Harlowe. If the statement is true, the *(if:)* section will be run. Otherwise, the *(else:)* section will be.

The [*(unless:)*](https://twine2.neocities.org/#macro_unless) macro can also be used in place of *(if:)* for the opposite effect. Furthermore, Boolean variables can be attached to hooks to control whether they're displayed, without an *(if:)*.

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

(unless: $animal is "dog")[It's a horse!]
(else:)[It's a dog!]

(set: $isDog to $animal is "horse")
$isDog[It's a dog!]
```

Download: <a href="harlowe_conditionalstatements_twee.txt" target="_blank">Twee Code</a>

