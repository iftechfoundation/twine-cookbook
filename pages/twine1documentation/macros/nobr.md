# `<<nobr>>`

The `<<nobr>>` macro removes all of the line breaks in the enclosed text.

## Usage

`<<nobr>> Text <<endnobr>>`

## Motivating example

In some cases, you'll want to do several things with macros at once. For example, in this passage:

>All you possess is an Axe (note under Weapons on your Action Chart) and a Backpack containing 1 Meal (note under Meals on your Action Chart).
>
>(Joe Dever, Flight from the Dark)

You'd probably want to set both the protagonist's weapon and number of meals. You can do this without any extraneous whitespace appearing in your story by putting all the `<<set>>` statements on the same line:

```twee
All you possess is an Axe and a Backpack containing 1 Meal. <<set $meals to 1>> <<set $weapon to "axe">>
```

This is not particularly readable, however. The `<<nobr>>` macro can help in these situations, like so:

```twee
All you possess is an Axe and a Backpack containing 1 Meal. <<nobr>>
<<set $meals to 1>>
<<set $weapon to "axe">>
<<endnobr>>
```

All the line breaks between `<<nobr>>` and `<<endnobr>>` are eliminated.

## See also

The nobr passage tag can be applied if you want every line break in the passage to be removed, without having to insert the macro tags around the entire text.

The `<<silently>>` macro was used for roughly the same purposes as «nobr» prior to version 1.4.0.
