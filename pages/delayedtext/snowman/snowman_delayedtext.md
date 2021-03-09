# "Delayed Text": Snowman (v1.3.0)

## Summary

"Delayed Text" uses the **[delay()](http://underscorejs.org/#delay)** function in Underscore combined with a [jQuery selector](https://api.jquery.com/category/selectors/) to target an element with the ID of "results" to change its internal text after five seconds.

## Example

[Download](snowman_delayedtext_example.html){: target="_top" download="snowman_delayedtext_example.html"}

## Twee Code

```twee
:: StoryTitle
Delayed Text in Snowman

:: Start
<div id="results"></div>
<%
 _.delay(
  function() {
    $("#results").text("It has been 5 seconds. Show the text!");
  },
  5000);
%>
```

[Twee Download](snowman_delayedtext_twee.txt){ target="_top" download="snowman_delayedtext_twee.txt"}

## See Also

[Typewriter Effect](../../typewriter/snowman/snowman_typewriter.md)
