# `<<endif>>`

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

`<<endif>>` closes the usage of the `<<if>>` macro.

## Usage

The `<<if>>` macro can be used in formats like these:

```twee
<<if expression>> Text <<endif>>
<<if expression>> Text <<else>> Text <<endif>>
<<if expression>> Text <<else if expression>> Text ... <<endif>>
```

*expression* is an expression that can evaluate to true or false. Text is any amount of passage text that you wish to display only if the condition is true. `<<endif>>` is a macro tag indicating the end of the `<<if>>` macro invocation.

Note that the Text can contain any Twine code, including an inner `<<if>>` invocation:

```twee
<<if $body is "wounded">>You are <<if $blood <= 5>>about to die<<else>>bleeding<<endif>>. Seek help <<endif>>
```
