# "Adding Functionality": Chapbook (v1.0.0)

## Summary

Chapbook allows for creation of custom inserts and modifiers. See [Adding Custom Inserts] and [Adding Custom Modifiers] in the [Chapbook Guide] for more details.

The example below adds an insert that displays a 😀 emoji, and a modifier that uppercases its text.

## Live Example

<section>
<iframe src="chapbook_adding_functionality_example.html" height=400 width=90%></iframe>


Download: <a href="chapbook_adding_functionality_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: Start
{embed passage: 'Extensions'}

[[See the new functionality]]

:: Extensions
[JavaScript]
// The preferred method is to add this to your story's JavaScript section.
// But since that is not is possible to encode in Twee formatting, we use
// the JavaScript modifier instead.

engine.extend('1.0.0', () => {
    config.template.inserts = [{
        match: /^smiley face$/i,
        render: () => '😀'
    }, ...config.template.inserts];
	
	config.template.modifiers = [{
        match: /^uppercase$/i,
        process(output) {
            output.text = output.text.toUpperCase();
        }
    }, ...config.template.modifiers];
});

:: See the new functionality
[uppercase]
Hello there {smiley face}
```

[Adding Custom Inserts]: https://klembot.github.io/chapbook/guide/advanced/adding-custom-inserts.html
[Adding Custom Modifiers]: https://klembot.github.io/chapbook/guide/advanced/adding-custom-modifiers.html
[Chapbook Guide]: https://klembot.github.io/chapbook/guide