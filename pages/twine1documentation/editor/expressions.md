# Expressions

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

**Expressions** are the ways data is provided to macros in stories. An expression is a lot like a mathematical formula. When a computer sees an expression, it simplifies it into a single value.

```twee
<<print 2 + 2>>
```

When Twine processes this `<<print>>` macro tag, it results in the number 4. This process is called *evaluation*.

```twee
<<print (1 + 2) * 4 + (3 + 2) / 5>>
```

This evaluates to the number 13. The computer follows the normal order of operations in mathematics: first multiplying and dividing, then adding and subtracting. *Sub-expressions* together and force them to be evaluated first with parentheses.

| Operator    | Function                                                             | Example                        |
| ----------- | -------------------------------------------------------------------- | ------------------------------ |
| `+`         | Addition.                                                            | `5 + 5` (is 10)                |
| `-`         | Subtraction. Can also be used to negate a number.                    | `5 - -5` (is 10)               |
| `*`         | Multiplication.                                                      | `5 * 5` (is 25)                |
| `/`         | Division.                                                            | `5 / 5` (is 1)                 |
| `%`         | Modulo (remainder of a division).                                    | `5 % 26` (is 1)                |
| `(` and `)` | Brackets/parentheses (causes an expression to be evaluated earlier). | `(5 + 10) * 2` (is 30, not 25) |

## Modulo

Modulo may seem somewhat obtuse an operator. Starting with a sequence of numbers: `0, 1, 2, 3, 4, 5, 6...`, and did `% 3` to each of them, they would become `0, 1, 2, 0, 1, 2, 0...` - that is, a constantly looping sequence. This ability to simplify rising sequences allows to perform some otherwise complicated calculations easily.

## Strings of Text

A string is a bunch of characters strung together, demarcated by matching pairs of either double or single quotes.

```twee
<<print "The" + ' former ' + "Prime Minister's">>
```

This expression pushes the strings together, and evaluates to "The former Prime Minister's". Notice that spaces had to be added between the words in order to produce a properly spaced final string. Also, notice that strings can *only* be added. They cannot be subtracted, multiplied, or divided.

## Printing Lists

Print content of lists:

```twee
<<set $myarray = ["this", "that"]>>
<<print $myarray.join(", ")>>
```

This will print the following:

```twee
this,that
```

### Functions

Twine has some built-in functions.

For instance, there exists a built-in function named `either()`, which randomly picks one of the values given to it.

```twee
You have found a pistol!
It's got <<print either(1,2,3,4,5,6)>> bullets.
```

## Logical Operators

Computers can perform more than just mathematical tasks - they are also virtuosos in classical logic. Much as how arithmetic involves manipulating numbers with addition, multiplication and such, logic involves manipulating the values "true" and "false" using its own operators. An expression that evaluates to "true" or "false" is called a **condition**

`is` is a logical operator that's short for 'equals.' Just as + adds the two numbers on each side of it, `is` compares two values on each side and evaluates to true or false depending on whether they're identical. It works equally well with strings and numbers, but beware -- the character "2" is not equal to the number 2.

| Operator(s) | Function                                                                       | Example                      |
| ----------- | ------------------------------------------------------------------------------ | ---------------------------- |
| `is`        | Evaluates to true if both sides are equal.                                     | `$bullets is 5`              |
| `neq`       | Evaluates to true if both sides are not equal.                                 | `$friends neq $enemies`      |
| `>`, `gt`   | Evaluates to true if the left side is greater than the right side.             | `$money > 3.75`              |
| `>=`, `gte` | Evaluates to true if the left side is greater than or equal to the right side. | `$apples >= $carrots + 5`    |
| `<`, `lt`   | Evaluates to true if the left side is less than the right side.                | `$shoes < $people * 2`       |
| `<=`, `lte` | Evaluates to true if the left side is less than or equal to the right side.    | `65 <= $age`                 |
| `and`       | Evaluates to true if both sides evaluates to true.                             | `$hasFriends and $hasFamily` |
| `or`        | Evaluates to true if either side is true.                                      | `$fruit or $vegetable`       |
| `not`       | Flips a true value to a false value, and vice versa.                           | `not visited("Waterfall")`   |
| `eq`        | An older synonym of `is` that is no longer recommended for use.                | `$fingers eq 5`              |

Conditions can quickly become complicated. The best way to keep things straight is to use parentheses to group things:

```twee
<<if ($master is 'Selator') and ($berries > 2)>>
```

### Use "is" instead of "="

Twine also supports using the keyword `is` for the use of `=` to set values. The `=` sign is a JavaScript operator which functions as a synonym of `to` used by the `<<set>>` macro, and causes unexpected behavior to occur if used outside of the macro.

(It should be noted that the Javascript double-equals sign `==` *can* be used as a synonym of `is`, but is not recommended for use as it is too easily confused with the single-equals sign.)

### Invalid "and" and "or" Usage

Care should be taken when writing expressions to remember what the "and" and "or" keywords are capable of.

An example:

```twee
<<if $health > 2 and < 4 >>
```

This macro tag's expression is **invalid** because the `>` and `<` operators (and indeed, all expression operators except `not`) require a distinct value to be on both sides of it. In a sense, the expression is interpreted as `($health > 2) and ( < 4)`, which is obviously nonsensical. It must be rewritten as `$health > 2 and $health < 4`.

Another example:

```twee
<<if $name is "Perone" or "Pavone" >>
```

This macro tag's expression is also **invalid**, for a different reason: it will be interpreted as `($name is "Perone") or ("Pavone")` - which is to say, it is true if `$name` is "Perone", or if the string "Pavone" is not false. This, of course, means that it's always true - an undesirable outcome. It must be rewritten as `$name is "Perone" or $name is "Pavone"`.

### Treating Numbers and Strings as Conditions

Some macros, such as `<<if>>`, are designed to only accept conditions. But, if such macros receive an expression, then, depending on the value, it can be treated as if it was a condition in and of itself. The number 0, and a string with no characters in it `""`, are both treated as `false`. The other numbers, and every other string, are treated as `true`. This means that you can simplify a number of expressions: `<<if $numberOfJavelins > 0>>` can simply become `<<if$numberOfJavelins>>`.
