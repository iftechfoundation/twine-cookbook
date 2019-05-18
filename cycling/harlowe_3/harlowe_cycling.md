# "Cycling Choices": Harlowe (v3.0)

## Summary

Starting in Harlowe 3.0.1, the [*(cycling-link)*](https://twine2.neocities.org/#macro_cycling-link) macro was introduced. Clicking on the link it provides allows for cycling though its possibilities. Combined with the [*bind*](https://twine2.neocities.org/#type_bind) keyword, its selection can be saved to a variable.

## Twee Code

```
:: StoryTitle
Harlowe 3: Cycling Links

:: Start
This cycling-link example remembers the choice made:
(cycling-link: bind $hair, "Black", "Brown", "Blonde", "Red", "White")

This cycling-link example does not:
(cycling-link: "Cat", "Dog", "Fish", "Mouse")

This cycling-link example will disappear (show empty string) on its last choice:
(cycling-link: "Two eggs", "One egg", "")

[[Show result]]

:: Show result
The choice of hair was $hair.


```

## See Also

[Setting and Showing Variables](../../settingandshowing/harlowe/harlowe_settingandshowing.md), [Modularity](../../modularity/harlowe/harlowe_modularity.md)
