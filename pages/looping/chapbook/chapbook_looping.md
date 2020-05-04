# "Looping": Chapbook (v1.0.0)

## Summary

In programming terminology, a "loop" is a common technique for iterating, moving through one by one, some type of data.

In Chapbook, the modifier `[JavaScript]` allows for using JavaScript inside a passage. Through using the **[forEach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)** function of Arrays and the **[write()](https://klembot.github.io/chapbook/guide/advanced/using-javascript-in-passages.html)** function supplied by Chapbook, each entry within an array can be shown.

## Example

[Download](chapbook_looping_example.html)

## Twee Code

```twee
:: StoryTitle
Chapbook: Looping

:: Start
exampleArray: [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61]
--

The values of the array are:
<ul>
[JavaScript]
exampleArray.forEach(function(value, index){
  write("<li>" + value + "</li>");
});
[continued]
</ul>

```

[Twee Download](chapbook_looping_twee.txt)
