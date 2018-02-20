# "Setting and Showing Variables": Harlowe (v2.0)

## Summary

Variables, symbols starting with ```$``` (for normal) or ```_``` (for temporary), can be "set" using the *[(set:)](https://twine2.neocities.org/#macro_set)* macro in Harlowe.

The keyword ```it``` can also be used as a shortcut for changing and saving a value in reference to itself. The ```it``` refers to the first variable named in the macro.

## Live Example

<section>
<iframe src="harlowe_settingandshowing_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_settingandshowing_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Setting and Showing Variables in Harlowe

:: Start
(set: $numberVariable to 5)
(set: $wordVariable to "five")
(set: $phraseVariable to "The value")

$phraseVariable is $numberVariable and $wordVariable.

(set: $numberVariable to it + 1)

$phraseVariable is $numberVariable and $wordVariable.
```

Download: <a href="harlowe_settingandshowing_twee.txt" target="_blank">Twee Code</a>

