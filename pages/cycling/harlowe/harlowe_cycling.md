# "Cycling Choices": Harlowe (v2.0)

!!! Information
    This example is affected by history changes in the story. Undoing or re-doing back to a passage containing this recipe has the potential to change its saved values.

## Summary

"Cycling Choices" demonstrates how to create a 'cycling' effect of different choices through clicking on them.

The cycle starts with the use of the [`(display:)`](https://twine2.neocities.org/#macro_display) macro and the assumption that the 1st element in the *$choices* [Array](https://twine2.neocities.org/#type_array) is the currently selected choice.

If the user clicks on the link (created through using the [`(link:)`](https://twine2.neocities.org/#macro_link) macro), the *$choices* array is updated using the [`(rotated:)`](https://twine2.neocities.org/#macro_rotated) macro. This causes the current 1st element to be moved to the end of the array, making the element that was previously 2nd to now be 1st.

At the end of every cycle, the currently selected value is always the 1st element in the *$choices* array.

## Example

[Download](harlowe_cycling_example.html){: target="_top" download="harlowe_cycling_example.html"}

## Twee Code

```twee
:: StoryTitle
Cycling Choices in Harlowe

:: Start
(set: $choices to (array: "First", "Second", "Third"))
Click options to cycle: [(display: "Cycling")]<choice|
[[Submit|Results]]

:: Cycling
{
  (link: (text: $choices's 1st) )[
    (set: $choices to (rotated: -1, ...$choices))
    (replace: ?choice)[(display: "Cycling")]
  ]
}

:: Results
Selected choice: (print: $choices's 1st)
```

[Twee Download](harlowe_cycling_twee.txt){ target="_top" download="harlowe_cycling_twee.txt"}

## See Also

[Setting and Showing Variables](../../settingandshowing/harlowe/harlowe_settingandshowing.md), [Modularity](../../modularity/harlowe/harlowe_modularity.md)
