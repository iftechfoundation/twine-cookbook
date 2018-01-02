# "Typewriter Effect": Snowman (v1.3.0)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary

"Typewriter Effect" demonstrates how to create a delayed character-by-character effect. In Snowman, this is achieved using recursive calls to the *[setTimeout()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)* function to repeat function calls every one second. A [jQuery selector](https://api.jquery.com/category/selectors/) is used to find an element with the ID "typewriter" whose HTML content is updated with the text every second until it is fully shown.

## Live Example

<section>
<iframe src="snowman_typewriter_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_typewriter_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Typewriter Effect in Snowman

:: UserScript[script]
// Create a new global object
window.typewriter = {};

// Save an index of the string.
// 	Start at -1 because it will be increased
//  once (to 0) before the first chracter is shown.
window.typewriter.index = -1;

// Allow users to set global text
window.typewriter.text = "";

// Save a reference to the setTimeout call
window.typewriter.timerReference = 0;

// Write text character by character to an element
//  with the ID "typewriter"
window.typewriter.write = function(){
	// Test if the index is less than the text length
		if(window.typewriter.index < window.typewriter.text.length) {
			// Update the current text character-by-character
		$("#typewriter").html(
			$("#typewriter").html() + window.typewriter.text[window.typewriter.index]
		);
			// Increase the index
		window.typewriter.index++;
			// Save the timeout reference
		window.typewriter.timerReference = setTimeout(window.typewriter.write, 1000);
	} else {
		// Clear out the timeout once index is greater than string length
		clearTimeout(window.typewriter.timerReference);
		// Reset the index
		window.typewriter.index = -1;
	}
	
}

:: Start
<div id="typewriter"></div>
<%
	window.typewriter.text = "Hello, world!";
	window.typewriter.write();
%>

```

Download: <a href="snowman_typewriter_twee.txt" target="_blank">Twee Code</a>
