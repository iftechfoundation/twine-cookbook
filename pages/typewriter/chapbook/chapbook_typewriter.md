# "Typewriter Effect": Chapbook (v1.0.0)

## Summary

"Typewriter Effect" demonstrates how to create a delayed character-by-character effect. In Chapbook, [new modifiers](https://klembot.github.io/chapbook/guide/advanced/adding-custom-modifiers.html) can be added through the *engine.extend()* function. This examples creates a new modifier called `[typewriter]` that accepts a time in milliseconds.

The `[typewriter]` modifier creates a series of `<span>` elements for each character found within the output of the modifier and sets an **[animation-delay](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay)** equal to the time given to the modifier multiplied by the position of the character within the total length of the text output. When used, each character will appear within the passage as if "typed" based on the time given to the modifier.

## Example

[Download](chapbook_typewriter_example.html)

## Twee Code

```twee
:: StoryTitle
Chapbook: Typewriter

:: Start
[JavaScript]
engine.extend('1.0.0', () => {
    config.template.modifiers = [{
        match: /^typewriter\s/i,
        process(output, {invocation}) {
      // Get the time
      let time = invocation.replace(/^typewriter\s/i, '');

      // Save original text
      let text = output.text;

      // Get length of original text
      let length = text.length;

      // Set initial index
      let index = 0;

      // Wipe out output to start
      output.text = "";

      // Loop through the text
      //  -- Add a new <span> for each character
      //  -- Set the class "fade-in"
      //  -- Set the delay as equal to time multiplied position
      for(let i = 0; i < length; i++) {
        output.text += `<span class='fade-in' style='animation-delay: ${time * i}ms'>${text[i]}</span>`;
      }

        }
    }, ...config.template.modifiers];
});
[continued]
[[Start TypeWriter]]

:: Start TypeWriter
[typewriter 1000]
Hello, world!
[continued]

```

[Twee Download](chapbook_typewriter_twee.txt)
