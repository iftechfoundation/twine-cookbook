# "Conditional Statements": Snowman (v1.3.0)

## Summary

Through using the ```s``` global variable and the built-in [Underscore template functionality](http://underscorejs.org/#template), JavaScript conditional statements can be run to show content in Snowman.

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

## See Also

[Setting and Showing Variables](../../settingandshowing/snowman/snowman_settingandshowing.md)
