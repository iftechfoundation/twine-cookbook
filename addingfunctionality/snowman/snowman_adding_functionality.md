# "Adding Functionality": Snowman (v1.3.0)

## Summary

Snowman does not provide [macros](../../terms/terms_macros.md). However, additional functionality can be added through the use of the [Underscore.js](https://underscorejs.org/) JavaScript library provided with Snowman.

In this example, a global function, *showCurrentTime()*, is added to the *window.setup* object. It is called in a passage through using the interpolation functionality of [Underscore's template system](https://underscorejs.org/#template) to show a value.

## Live Example

<section>
<iframe src="snowman_adding_functionality_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_adding_functionality_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Adding Functionality in Snowman

:: UserScript[script]
// Use or create window.setup
window.setup = window.setup || {};

// Create global function
window.setup.showCurrentTime = function() {
	return new Date();
}

:: Start
The current time is <%= setup.showCurrentTime() %>

```

Download: <a href="snowman_adding_functionality_twee.txt" target="_blank">Twee Code</a>
