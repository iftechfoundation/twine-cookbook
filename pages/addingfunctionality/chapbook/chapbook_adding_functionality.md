# "Adding Functionality": Chapbook (v1.0.0)

## Summary

Chapbook allows for creation of [custom inserts and modifiers](https://klembot.github.io/chapbook/guide/advanced/adding-custom-inserts.html).

The example below adds an insert that displays a 😀 emoji.

## Live Example

<section>
<iframe src="chapbook_adding_functionality_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_adding_functionality_example.html" target="_blank">Live Example</a>
</section>

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

Download: <a href="chapbook_adding_functionality_twee.txt" target="_blank">Twee Code</a>
