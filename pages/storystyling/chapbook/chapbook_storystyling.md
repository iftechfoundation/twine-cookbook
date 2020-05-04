# "Variable Story Styling": Chapbook (v1.0.0)

## Summary

Using the [`[CSS]`](https://klembot.github.io/chapbook/guide/advanced/using-css-in-passages.html) modifier in Chapbook, it is possible to combine expressions with variables and change the text and background colors dynamically. This examples creates a variable *color* and changes its value in the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) of two passages.

## Example

[Download](chapbook_storystyling_example.html)

## Twee Code

```twee
:: StoryTitle
Chapbook: Variable Story Styling

:: Start
color: "green"
--

[CSS]
#page article {
    color: {color};
}

[continued]
This text will be in green.

[[Switch to red text]]

:: Switch to red text
color: "red"
--
[CSS]
#page article {
    color: {color};
}

[continued]
This text will be in red.

[[Switch to green text->Start]]

```

[Twee Download](chapbook_storystyling_twee.txt)
