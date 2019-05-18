# "Looping": SugarCube (v2.18)

## Summary

In programming terminology, a "loop" is a common technique for iterating, moving through one by one, some type of data. In SugarCube, the control macro [&lt;&lt;for&gt;&gt;](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-for) provides this functionality. It acts like the [“for” keyword in JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for) and its usage works in a similar way.

In this example, the array *arrayInventory* is set to the series of strings "Bread", "Pan", and "Book". Using the &lt;&lt;for&gt;&gt; macro, a temporary variable is set to 0 and increased for each loop until its value is no longer less than the [length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length) (number of entries) in the array. Inside the macro, the text is shown each time with the value of the entry matching the position of the value of *_i* in the array substituted.

## Twee Code

```
:: StoryTitle
Looping in SugarCube

:: Start
<!-- Set the variable $arrayInventory to the array containing "Bread", "Pan", "Book" -->
<<set $arrayInventory to ["Bread", "Pan", "Book"]>>

<!-- Set the temporary variable _l to 0 and increase it until it is greater than the length of the array $arrayInventory -->
<<for _i to 0; _i lt $arrayInventory.length; _i++>>
You have $arrayInventory[_i]
<</for>>

```
