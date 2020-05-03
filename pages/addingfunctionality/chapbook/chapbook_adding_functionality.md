# "Adding Functionality": Chapbook (v1.0.0)

## Summary

Chapbook allows for creation of [custom inserts and modifiers](https://klembot.github.io/chapbook/guide/advanced/adding-custom-inserts.html).

The example below adds an insert that displays a 😀 emoji.

## Example

[Download Example](chapbook_adding_functionality_example.html)

## Twee Code

```twee
:: StoryTitle
Adding Functionality

:: UserScript[script]
engine.extend('1.0.0', () => {
    config.template.inserts = [{
        match: /^smiley face$/i,
        render: () => '😀'
    }, ...config.template.inserts];
});

:: Start
Hello there {smiley face}

```

[Download Twee Code](chapbook_adding_functionality_twee.txt)
