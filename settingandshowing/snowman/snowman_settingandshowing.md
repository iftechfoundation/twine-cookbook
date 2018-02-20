# "Setting and Showing Variables": Snowman (v1.3.0)

## Summary

In Snowman, the ```s``` global variable can be used to store and retrieve values. Properties can be created and assigned freely. The [Underscore template functionality](http://underscorejs.org/#template) can be used to define, change, and show the values of variables. 

## Live Example

<section>
<iframe src="snowman_settingandshowing_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_settingandshowing_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Setting and Showing Variables in Snowman

:: Start
<%
	s.numberVariable = 5;
	s.wordVariable = "five";
	s.phraseVariable = "The value";
%>

<%= s.phraseVariable %> is <%= s.numberVariable %> and <%= s.wordVariable %>.

<%
	s.numberVariable++;
%>

<%= s.phraseVariable %> is <%= s.numberVariable %> and <%= s.wordVariable%>.

```

Download: <a href="snowman_settingandshowing_twee.txt" target="_blank">Twee Code</a>

