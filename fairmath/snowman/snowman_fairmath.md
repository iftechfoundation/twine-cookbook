# "Fairmath System": Snowman (v1.3.0)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary

"Fairmath System" demonstrates how to re-create the Fairmath system found [in ChoiceScript](http://choicescriptdev.wikia.com/wiki/Arithmetic_operators#Fairmath). Based on a percentage operation, increase and decrease changes the value by a percentage as the difference between the original and adjusted value.

This example uses functions *increase()* and *decrease()* as part of a created global *window.twine*. These can be called through using the [Underscore template functionality](http://underscorejs.org/#template) to define, use, and show the values of the functions in any one passage.

## Live Example

<section>
<iframe src="snowman_fairmath_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_fairmath_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Fairmath in Snowman

:: UserScript[script]
window.twine = {};
	
window.twine.increase = function(x,y) {
	return Math.round(x+((100-x)*(y/100)));
};
	
window.twine.decrease = function(x,y) {
	return Math.round(x-(x*(y/100)));
};

:: Start
Decrease 100 by 50% using Fairmath:
<%= window.twine.decrease(100, 50) %>

Increase 50 by 50% using Fairmath:
<%= window.twine.increase(50, 50) %>

```

Download: <a href="snowman_fairmath_twee.txt" target="_blank">Twee Code</a>

