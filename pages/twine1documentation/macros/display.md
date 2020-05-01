# `<<display>>`

The `<<display>>` macro lets you display the full contents of a passage inside another passage.

## Usage

Long form:

`<<display expression>>`

Shorthand form (see below):

`<<string [value …]>>`

## Motivating example

Suppose you have a block of text or code which appears identically in multiple passages. It can be a pain to have to keep track of each instance in which it was used, especially when fixing spelling or link names. `<<display>>` provides you with an elegant means of reusing this text: simply place it in another passage, and then use `<<display>>` in each of the places it is used.

## A note about tags

What the `<<display>>` macro actually does is copy the text from the given passage into the current passage. It doesn't actually display the passage in its own right. What this means is that, if a passage has tag-based CSS styling specific to it, then that styling will not be applied to the current passage!

## Using a variable to display a passage

The `<<display>>` macro treats its argument as a code expression. This means that you can put a passage name in a variable and then display it:

With a rush of wind, you arrive in the `<<print $destination>>`!

`<<display $destination>>`

If, say, *$destination* contained the string "Cellar", and a Cellar passage existed, it would print "With a rush of wind, you arrive in the Cellar!" and display the Cellar passage.

## Shorthand form

The `<<display>>` macro is special among Twine macros because it has a shorthand form. Instead of writing `<<display "passage">>`, you can simply write `<<passage>>`, as if it was another macro.

However, to avoid conflicts with other aspects of Twine syntax, you can only use the shorthand to display passages whose names adhere to these rules:

- The passage name must not contain spaces.
- The passage name must not conflict with the name of an actual macro (so, you can't display a passage titled "print").

## Displaying a script passage

If you attempt to `<<display>>` a passage containing a Javascript script, something special will happen: the script code will not be displayed, but will instead be re-executed.

## Avoid the `<<display>>` loop

It is possible to lock up a reader's Web browser by using the «display» macro improperly, like this:

```twee
:: Oops
<<display "Oops">>
```

When displayed, the passage will keep attempting to display itself over and over until the reader force quits his Web browser. This doesn't do permanent damage, but it will not endear yourself to your reader.
