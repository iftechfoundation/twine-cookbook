# "Fairmath System": Chapbook (v1.0.0)

## Summary

"Fairmath System" demonstrates how to re-create the Fairmath system found [in ChoiceScript](http://choicescriptdev.wikia.com/wiki/Arithmetic_operators#Fairmath). Based on the operation, increasing and decreasing changes the value by a percentage as the difference between the original and adjusted value.

This example defines functions in the Story JavaScript, which are then used in the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) of a passage to set values. These are shown using [expressions](https://klembot.github.io/chapbook/guide/state/displaying-variables.html) within the text of the passage itself.

## Example

[Download](chapbook_fairmath_example.html){: target="_top" download="chapbook_fairmath_example.html"}

## Twee Code

```twee
:: StoryTitle
Chapbook: Fairmath

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
decreaseExample: setup.fairmath.decrease(100, 50)
increaseExample: setup.fairmath.increase(50, 50)
--

Decrease 100 by 50% using Fairmath:
Decrease Example: {decreaseExample}

Increase 50 by 50% using Fairmath:
Increase Example: {increaseExample}

```

[Twee Download](chapbook_fairmath_twee.txt){ target="_top" download="chapbook_fairmath_twee.txt"}
