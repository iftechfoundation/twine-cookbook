# "Deleting Variables": Snowman (v1.3)

## Summary

Through using the [Underscore template library](https://underscorejs.org/#template) available in Snowman, JavaScript can be used within passages without a `<script>` tag. The **[delete](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete)** operator can be used in JavaScript to remove a variable.

## Example

[Download](snowman_deletingvariables_example.html){: target="_top" download="snowman_deletingvariables_example.html"}

## Twee Code

```twee
:: StoryTitle
Snowman: Deleting Variables

:: UserScript[script]
window.story = {};

window.story.example = "an example!";

:: Start
What is the value of the property "example" of the object window.story? <%= window.story.example %>

[[Delete the value!]]

:: Delete the value!
<%

// Delete the variable
delete window.story.example;

%>

[[Test for value]]

:: Test for value
Does "example" still exist as part of the object window.story? <%= window.story.hasOwnProperty("example") %>

```

[Twee Download](snowman_deletingvariables_twee.txt){ target="_top" download="snowman_deletingvariables_twee.txt"}
