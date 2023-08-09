# "Looping": Snowman (v1.3.0)

## Summary

In programming terminology, a "loop" is a common technique for iterating, moving through one by one, some type of data. Because Snowman does not provide macros, the existing JavaScript **[for](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)** keyword can be used to create loops. Since Snowman also includes the Underscore.js and jQuery libraries, the **[_.each()](http://underscorejs.org/#each)** and **[jQuery.each()](http://api.jquery.com/jquery.each/)** functions can also be used.

In this example, the *s* global shortcut to the *[window.story.state](https://videlais.github.io/snowman/#/1/window_story/properties/state)* variable used. A new property called "arrayInventory" is set to the series of values "Bread", "Pan", and "Book". The first example uses the JavaScript **for** keyword to move through the values. The second example uses the **_.each()** function in Underscore.js, and the third uses the **jQuery.each()** function for the same purpose.

## Live Example

[Download](snowman_looping_example.html){: target="_top" download="snowman_looping_example.html"}

## Twee Code

```twee
:: StoryTitle
Looping in Snowman

:: Start
<%
// An array of the strings "Bread", "Pan", "Book"
s.arrayInventory = ["Bread", "Pan", "Book"];

// An example using JavaScript
for (var i = 0; i < s.arrayInventory.length; i++){
 %>You have <%= s.arrayInventory[i] %>.<br> <%
}
%>

<hr>
<%
// An example using Underscore.js
_.each(s.arrayInventory, function(item) {
    %>You have <%= item %>.<br> <%
});
%>

<hr>
<%
// An example using jQuery
jQuery.each(s.arrayInventory, function( index, value ) {
   %>You have <%= value %>.<br> <%
});

%>

```

[Twee Download](snowman_looping_twee.txt){ target="_top" download="snowman_looping_twee.txt"}
