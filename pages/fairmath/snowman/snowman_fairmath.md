# "Fairmath System": Snowman (v1.3.0)

## Summary

"Fairmath System" demonstrates how to re-create the Fairmath system found [in ChoiceScript](http://choicescriptdev.wikia.com/wiki/Arithmetic_operators#Fairmath). Based on a percentage operation, increase and decrease changes the value by a percentage as the difference between the original and adjusted value.

This example uses functions **increase()** and **decrease()** as part of a created global *window.setup.fairmath*. These can be called through using the [Underscore template functionality](http://underscorejs.org/#template) to define, use, and show the values of the functions in any one passage.

## Example

[Download](snowman_fairmath_example.html){: target="_top" download="snowman_fairmath_example.html"}

## Twee Code

```twee
:: StoryTitle
Fairmath in Snowman

:: UserScript[script]
// Create a global object
window.setup = window.setup || {};

// Create a fairmath global object
window.setup.fairmath = {};

// Create an 'increase' function
setup.fairmath.increase = function(x,y) {
  return Math.round(x+((100-x)*(y/100)));
};

// Create a "decrease" function
setup.fairmath.decrease = function(x,y) {
  return Math.round(x-(x*(y/100)));
};

:: Start
Decrease 100 by 50% using Fairmath:
<%= setup.fairmath.decrease(100, 50) %>

Increase 50 by 50% using Fairmath:
<%= setup.fairmath.increase(50, 50) %>

```

[Twee Download](snowman_fairmath_twee.txt){ target="_top" download="snowman_fairmath_twee.txt"}
