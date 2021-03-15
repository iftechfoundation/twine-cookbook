# "Setting and Showing Variables": Snowman (v1.3.0)

## Summary

In Snowman, the *s* global variable can be used to store and retrieve values. Properties can be created and assigned freely. The [Underscore template functionality](http://underscorejs.org/#template) can be used to define, change, and show the values of variables.

## Example

[Download](snowman_settingandshowing_example.html){: target="_top" download="snowman_settingandshowing_example.html"}

## Twee Code

```twee
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

[Twee Download](snowman_settingandshowing_twee.txt){ target="_top" download="snowman_settingandshowing_twee.txt"}
