# "Looping": Harlowe (v2.0)

## Summary

In programming terminology, a "loop" is a common technique for iterating, moving through one by one, some type of data. In Harlowe, the macros [`(loop:)`](https://twine2.neocities.org/#macro_loop) and [`(for:)`](https://twine2.neocities.org/#macro_for) provide this functionality. Combined with the keywords [`each`](https://twine2.neocities.org/#type_lambda), to move through all entries, or "where," to specify some condition, they allow for "looping" through data structures like arrays or datamaps.

In this example, the variable *arrayInventory* is set to the value of an array containing the strings "Bread", "Pan", and "Book". The `(for:)` macro is used with the keyword `each` to set the values contained in the array to the temporary variable *_temp* for each value of the [spread out](https://twine2.neocities.org/#type_array) array. The text contained in the associated hook to the `(for:)` macro is shown each loop with the value of *_temp* changed for each value in the array.

## Live Example

<section>
<iframe src="harlowe_looping_example.html" height=400 width=90%></iframe>

Download: <a href="harlowe_looping_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```twee
:: StoryTitle
Looping in Harlowe

:: Start
<!-- Create an array of the strings "Bread", "Pan", "Book" -->
(set: $arrayInventory to (a: "Bread", "Pan", "Book") )

<!-- For each entry in the expanded array in turn, -->
<!--  set the entry to the temporary variable _temp -->
(for: each _temp, ...$arrayInventory)[
You have _temp.]


```

Download: <a href="harlowe_looping_twee.txt" target="_blank">Twee Code</a>
