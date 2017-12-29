# "Fairmath System": Snowman (v1.3.0)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary

"Fairmath System" demonstrates how to re-create the Fairmath system found [in ChoiceScript](http://choicescriptdev.wikia.com/wiki/Arithmetic_operators#Fairmath). Based on a percentage operation, addition and subtraction changes the value by a percentage as the difference between the original and adjusted value.

This example uses functions *addition()* and *subtraction()* and the [Underscore template functionality](http://underscorejs.org/#template) to define, use, and show the values of the functions.

## Live Example

<section>
<iframe src="snowman_fairmath_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_fairmath_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Fairmath in Snowman

:: Start
<%

function addition(x,y) {
	return Math.round(x+((100-x)*(y/100)));
}
	
function subtraction(x,y) {
	return Math.round(x-(x*(y/100)));
}

%>

Subtract 50 using fairmath from an initial value of 100:
<%= subtraction(100, 50) %>

Add 100 using fairmath from an initial value of 50:
<%= addition(50, 100) %>


```

Download: <a href="snowman_fairmath_twee.txt" target="_blank">Twee Code</a>

