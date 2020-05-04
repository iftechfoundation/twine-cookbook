# "Arrays": Harlowe (v2.1)

## Summary

[Arrays](https://twine2.neocities.org/#type_array) are a collection of values. Each entry in an array is assigned an *index*, which is a number that corresponds to its position in the array. In Harlowe, and unlike in JavaScript, arrays are one-based, meaning the first element in the array is given the index "1". Arrays can be created using the `(a:)` or `(array:)` macro and assigning a variable to it: `(set: $myArray to (a:))`.

Specific elements in an array can be accessed by following its variable name with a possessive `'s` and an ordinal number referencing the index to check, (`$myArray's 2nd`); the final entry, `$myArray's last`, points to the final element. Its contents can be tested using the `contains` operator (e.g. `(if: $myArray contains 'something')[...]`), add new items using the `+` operator (e.g. `(set: $myArray to + (a: 'something'))`), and remove items using the `-` operator. All elements in an array can be passed to macros as separate arguments with the spread operator (`...`).

## Example

[Download](harlowe_arrays_example.html)

## Twee Code

```twee
:: StoryTitle
Arrays in Harlowe

:: init [startup]
<!-- it is always a good idea to initialize your variables, but with arrays it is particularly important -->
(set: $inventory to (a:))
(set: $chest to (a: 'a shield', 'a suit of armor'))
(set: $chestOpen to false)

:: inventory [header]
You are currently carrying:
<!-- if the inventory contains nothing, show "nothing" -->\
(if: $inventory's length is 0)[\
    nothing.
](else:)[\
    <!-- we iterate over the array and print each item -->\
    (for: each _item, ...$inventory)[\
        _item (unless: $inventory's last is _item)[, ]\
    ].
]
-----


:: Start
<!-- we use the + operator and wrap the target elements in an (a:) macro to add to the array -->\
You find yourself inside a small room. In the corner, you see a sword, and decide to pick it up.

(set: $inventory to it + (a: 'a sword'))\
[[Continue|hallway]]

:: hallway
You see a chest here in the hallway.  \
(unless: $chestOpen)[\
    Do you want to open it?

    {
    (link: 'Open the chest.')[
        <!-- adding to arrays together can also be done with the + operator -->
        (set: $inventory to it + $chest)
        (set: $chestOpen to true)
        (goto: 'chest')
    ]
    }
](else:)[\
    It's open, and there's nothing inside.
]\

[[Move on.|dart trap]]

:: chest
You open the chest and find (for: each _item, ...$chest)[\
    _item (unless: $chest's last is _item)[ and ]\
].

(link: 'Okay')[ (goto: (history:)'s last) ]

:: dart trap
Several darts shoot out of a wall at you!
<!-- we can check to see if the player has a given item with the contains operator -->
(if: $inventory contains 'a shield')[\
    Luckily, your shield will protect you.
](else:)[\
    With no way to defend yourself, you die.
]
```

[Twee Download](harlowe_arrays_twee.txt)
