# "Passages in Passages": Harlowe (v1.0)

## Summary

The Harlowe story format allows for content in one passage to be displayed in another through the use of the [`(display:)`](https://twine2.neocities.org/#macro_display) macro. Given the name of an existing passage, its contents will added wherever the macro is called.

## Example

[Download](harlowe_passagesinpassages_example.html){: target="_top" download="harlowe_passagesinpassages_example.html"}

## Twee Code

```twee
:: StoryTitle
Harlowe: Passages in Passages

:: Start
This is the Start passage!
(display: "Another")

:: Another
And this is another passage!

```

[Twee Download](harlowe_passagesinpassages_twee.txt){ target="_top" download="harlowe_passagesinpassages_twee.txt"}
