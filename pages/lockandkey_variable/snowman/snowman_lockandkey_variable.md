# "Lock and Key: Variable": Snowman (v1.3)

## Summary

"Lock and Key: Variable" demonstrates how to create the effect of picking up a key and unlocking a door. In this example, the key is a variable (*s.key*) and does not initially exist in the Start passage.

When the link "Pick up the key" is clicked, *s.key* is changed to the value "true" and the door link changes from its initial response of "Locked Door" to a link to the passage Exit.

## Example

[Download](snowman_lockandkey_variable_example.html){: target="_top" download="snowman_lockandkey_variable_example.html"}

## Twee Code

```twee
:: StoryTitle
Lock and Key: Variable in Snowman

:: Start
Rooms:
- [[Front Room]]
- [[Back Room]]

:: Front Room
<% if (s.key) { %>
[[Exit]]
<% } else { %>
*Locked Door*
<% } %>

Rooms:
- [[Back Room]]

:: Back Room
<% if (!s.key) { %>
Items:
- <a href="javascript:void(0)" class="key-item">Pick up key</a>
<% } else { %>
There is nothing here.
<% } %>

<%
$(function() {
  $('.key-item').click(function() {
    s.key = true;
    $(this).replaceWith('<span>You have a key.</span>');
  });
});
%>

Rooms:
- [[Front Room]]

:: Exit
You found the key and went through the door!


```

[Twee Download](snowman_lockandkey_variable_twee.txt){ target="_top" download="snowman_lockandkey_variable_twee.txt"}

## See Also

[Setting and Showing Variables](../../settingandshowing/snowman/snowman_settingandshowing.md)
