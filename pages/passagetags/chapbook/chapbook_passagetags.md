# "CSS and Passage Tags": Chapbook (v1.0.0)

## Summary

Using the built-in global variable *config*, [text colors and other CSS properties](https://klembot.github.io/chapbook/guide/customization/fonts-and-colors.html) can be programmatically adjusted using the [`[JavaScript]`](https://klembot.github.io/chapbook/guide/advanced/using-javascript-in-passages.html) modifier in Chapbook.

## Example

[Download](chapbook_passagetags_example.html)

## Twee Code

```twee
:: StoryTitle
Chapbook: CSS and Passage Tags

:: Start
config.style.page.color: "yellow-4"
--
This is one color!
[JavaScript]
// Overwrite the default text color
config.style.page.color = "violet-6";
[continued]

And this is the same color!

```

[Twee Download](chapbook_passagetags_twee.txt)
