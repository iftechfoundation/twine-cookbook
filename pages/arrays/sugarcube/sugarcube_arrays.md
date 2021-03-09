# "Arrays": SugarCube (v2.18)

## Summary

Arrays are a collection of values. Each value in an array is assigned an *index*, which is a number that corresponds to the position of that item or element. Arrays have many built-in methods and other features, and [SugarCube adds many more](http://www.motoslave.net/sugarcube/2/docs/object-methods.html#array). Arrays can be created by assigning a variable to the array literal, which is a pair of brackets (`[]`): `<<set $myArray to []>>`.

[Specific elements](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Accessing_array_elements) can be accessed in an array by following its variable name with a pair of brackets containing the index to check. Testing whether an array contains an element can be done using the **[Array#includes()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)**  function; adding new items can be done using the **[Array#push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)** function.

## Example

[Download](sugarcube_arrays_example.html){ target="_top" download="sugarcube_arrays_example.html"}

## Twee Code

```twee
:: StoryTitle
Arrays in SugarCube

:: StoryInit
/% it is always a good idea to initialize your variables, but with arrays it is particularly important %/
<<set $inventory to []>>
<<set $chest to ['a shield', 'a suit of armor']>>
<<set $chestOpen to false>>

:: PassageHeader
You are currently carrying:
/% if the inventory contains nothing, show "nothing" %/\
<<if $inventory.length is 0>>\
    nothing.
<<else>>\
    /% the Array#join() method combines all array elements into a single string, with each element separated by the argument given %/\
    <<= $inventory.join(', ')>>.
<</if>>
-----


:: Start
/% we use the Array#push() method to add new items to our inventory array %/\
You find yourself inside a small room. In the corner, you see a sword, and decide to pick it up.

<<run $inventory.push('a sword')>>\
[[Continue|hallway]]

:: hallway
You see a chest here in the hallway.  \
<<if not $chestOpen>>\
    Do you want to open it?

    <<link [[Open the chest.|chest]]>>
        /% concatenating the arrays and setting the result to $inventory moves all the items from the $chest array into the $inventory array %/
        <<set $inventory to $inventory.concat($chest)>>
        <<set $chestOpen to true>>
    <</link>>
<<else>>\
    It's open, and there's nothing inside.
<</if>>

[[Move on.|dart trap]]

:: chest
You open the chest and find <<= $chest.join(' and ')>>.

[[Okay.|previous()]]

:: dart trap
Several darts shoot out of a wall at you!
/% we can check to see if the player has a given item with Array#includes() %/
<<if $inventory.includes('a shield')>>\
    Luckily, your shield will protect you.
<<else>>\
    With no way to defend yourself, you die.
<</if>>
```

[Twee Download](sugarcube_arrays_twee.txt){ target="_top" download="sugarcube_arrays_twee.txt"}
