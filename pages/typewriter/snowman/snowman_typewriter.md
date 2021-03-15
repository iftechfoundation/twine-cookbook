# "Typewriter Effect": Snowman (v1.3.0)

## Summary

"Typewriter Effect" demonstrates how to create a delayed character-by-character effect. In Snowman, this is achieved using recursive calls to the *[setTimeout()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)* function to repeat calls once every one second. A [jQuery selector](https://api.jquery.com/category/selectors/) is used to find an element with the ID "typewriter" whose HTML content is updated with the text every second until it is fully shown.

## Example

[Download](snowman_typewriter_example.html){: target="_top" download="snowman_typewriter_example.html"}

## Twee Code

```twee
:: StoryTitle
Typewriter Effect in Snowman

:: UserScript[script]
// Create a global setup object
window.setup = window.setup || {};

// Add a 'typewriter' object
setup.typewriter = {};

// Save an index of the string.
// Start at -1 because it will be increased
//  once (to 0) before the first character is shown.
setup.typewriter.index = -1;

// Allow users to set global text
setup.typewriter.text = "";

// Save a reference to the setTimeout call
setup.typewriter.timerReference = 0;

// Write text character by character to an element
//  with the ID "typewriter"
setup.typewriter.write = function(){
  // Test if the index is less than the text length
    if(setup.typewriter.index < setup.typewriter.text.length) {
      // Update the current text character-by-character
    $("#typewriter").html(
      $("#typewriter").html() + setup.typewriter.text[setup.typewriter.index]
    );
      // Increase the index
    setup.typewriter.index++;
      // Save the timeout reference
    setup.typewriter.timerReference = setTimeout(setup.typewriter.write, 1000);
  } else {
    // Clear out the timeout once index is greater than string length
    clearTimeout(setup.typewriter.timerReference);
    // Reset the index
    setup.typewriter.index = -1;
  }
  
}

:: Start
<div id="typewriter"></div>
<%
  setup.typewriter.text = "Hello, world!";
  setup.typewriter.write();
%>

```

[Twee Download](snowman_typewriter_twee.txt){ target="_top" download="snowman_typewriter_twee.txt"}

## See Also

[Delayed Text](../../delayedtext/snowman/snowman_delayedtext.md)
