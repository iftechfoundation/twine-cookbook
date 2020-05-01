# "Static Healthbars": Snowman (v1.3)

## Summary

"Static Healthbars" demonstrates how to write HTML elements using variable values. In this example, [Underscore template](https://underscorejs.org/#template) functionality is used to create `<progress>` and `<meter>` elements.

## Live Example

<section>
<iframe src="snowman_statichealthbars_example.html" height=400 width=90%></iframe>

Download: <a href="snowman_statichealthbars_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```twee
:: StoryTitle
Static Healthbars in Snowman

:: Start
<% 
	window.setup = {};
	window.setup.health = 80;
%>

Show a healthbar using a Progress element:
<%= '<progress value="' + window.setup.health + '" max="100"></progress>' %>

Show a healthbar using a Meter element:
<%= '<meter value="' + window.setup.health + '" min="0" max="100"></meter>' %>

```

Download: <a href="snowman_statichealthbars_twee.txt" target="_blank">Twee Code</a>
