# "Delayed Text": Harlowe (v2.0)

## Summary

"Delayed Text" uses the [`(live:)`](https://twine2.neocities.org/#macro_live) and [`(stop:)`](https://twine2.neocities.org/#macro_stop) macros to create a loop that runs only once with a delay of five seconds.

## Example

[Download](harlowe_delayedtext_example.html){: target="_top" download="harlowe_delayedtext_example.html"}

## Twee Code

```twee
:: StoryTitle
Delayed Text in Harlowe

:: Start
{
 (live: 5s)[
    (stop:)
    It has been 5 seconds. Show the text!
 ]
}
```

[Twee Download](harlowe_delayedtext_twee.txt){ target="_top" download="harlowe_delayedtext_twee.txt"}

## See Also

[Typewriter Effect](../../typewriter/harlowe/harlowe_typewriter.md)
