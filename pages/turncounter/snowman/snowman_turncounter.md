# "Turn Counter": Snowman (v1.3.0)

## Summary

"Turn Counter" demonstrates the use of the *window.story.history* array in keeping track of "turns" (number of passages visited). The ***[window.story.render()](https://videlais.github.io/snowman/#/1/window_story/functions/render)*** function is used to "display" or otherwise include another passage at the start of each.

In this example, the *length* of the array *[window.story.history](https://videlais.github.io/snowman/#/1/window_story/properties/history)* is compared to its modulo 24 value. Sometimes known as "wrap around," the modulus operator (%) is used to get the remainder of the number of "turns" (passages) divided by 24. This creates a clock where its value shows one of a series of strings representing "morning", "mid-morning", "afternoon", or "night."

By visiting other passages, the turn count is increased and the hour reaches 23 before being reset back to 0 before increasing again.

## Example

[Download](snowman_turncounter_example.html){: target="_top" download="snowman_turncounter_example.html"}

## Twee Code

```twee
:: StoryTitle
Turn Counter in Snowman

:: Start
<%=  window.story.render("Turn Counter") %>
Rooms:

[[Back Room]]

[[Left Room]]

[[Right Room]]

:: Back Room
<%=  window.story.render("Turn Counter") %>
Rooms:

[[Left Room]]

[[Right Room]]

[[Front Room|Start]]

:: Left Room
<%=  window.story.render("Turn Counter") %>
Rooms:

[[Right Room]]

[[Back Room]]

[[Front Room|Start]]


:: Right Room
<%=  window.story.render("Turn Counter") %>
Rooms:

[[Left Room]]

[[Back Room]]

[[Front Room|Start]]


:: Turn Counter
<%
  var hour = window.story.history.length % 24;

  if(hour <= 8){%>
    It is morning.
  <%}
  if(hour > 8 && hour <= 12){%>
    It is mid-morning.
  <%}
  if(hour > 12 && hour <= 16){%>
    It is afternoon.
  <%}
  if(hour > 16){%>
    It is night.
  <%}
%>

```

[Twee Download](snowman_turncounter_twee.txt){ target="_top" download="snowman_turncounter_twee.txt"}
