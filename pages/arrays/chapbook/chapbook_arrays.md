# "Arrays": Chapbook (1.0.0)

## Summary

Using the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html), variables can be set using any JavaScript values, such as [arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array). However, Chapbook expressions will only [show certain types of values](https://klembot.github.io/chapbook/guide/state/displaying-variables.html).

While Chapbook cannot show an array or its value by position, a new variable can be set and then shown. This following example shows how to do this approach.

## Example

[Download](chapbook_arrays_example.html){: target="_top" download="chapbook_arrays_example.html"}

## Twee Code

```twee
:: StoryTitle
Arrays for Chapbook

:: Start
arrayExample: [13, 15]
exampleValue: arrayExample[0]
--
Chapbook can't display indexed array values currently. However, setting a value based on a position in an array will show.

Here is an {exampleValue}.

```

[Twee Download](chapbook_arrays_twee.txt){ target="_top" download="chapbook_arrays_twee.txt"}
