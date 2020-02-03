# "Conditional Statements": Snowman (v1.3.0)

## Summary

Through using the *s* global variable and the built-in [Underscore template functionality](http://underscorejs.org/#template), JavaScript conditional statements can be run to show content in Snowman.

## Live Example

<section>
<iframe src="snowman_conditionalstatements_example.html" height=400 width=90%></iframe>

Download: <a href="snowman_conditionalstatements_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Conditional Statements in Snowman

:: Start
<%
	s.animal = "horse";
%>

<% if(s.animal == "dog"){ %>
It's a dog!
<% } else { %>
It's a horse!
<% } %>
```

Download: <a href="snowman_conditionalstatements_twee.txt" target="_blank">Twee Code</a>

## See Also

[Setting and Showing Variables](../../settingandshowing/snowman/snowman_settingandshowing.md)

