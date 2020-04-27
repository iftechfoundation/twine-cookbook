# "Dropdown": Harlowe (v3.0)

## Summary

The macro [`(dropdown:)`](https://twine2.neocities.org/#macro_dropdown) was introduced with Harlowe 3.0. It creates a drop-down menu based on the options supplied to it. In order to save the outcome of using the drop-down menu, the keyword [`bind`](https://twine2.neocities.org/#type_bind) is used to save the choice.

## Live Example

<section>
<iframe src="harlowe_dropdown_example.html" height=400 width=90%></iframe>

Download: <a href="harlowe_dropdown_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```twee
:: StoryTitle
Harlowe 3: Dropdown

:: Start
Choose direction:
(dropdown: bind $direction, "Up", "Down", "Left", "Right")

[[Show result]]

:: Show result
The direction picked was $direction.


```

Download: <a href="harlowe_dropdown_twee.txt" target="_blank">Twee Code</a>
