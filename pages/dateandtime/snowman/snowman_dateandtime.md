# "Date and Time": Snowman (v1.3)

## Summary

"Date and Time" demonstrates how to use the JavaScript *[Date()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)* functionality in Snowman.

## Example

[Download](snowman_dateandtime_example.html){: target="_top" download="snowman_dateandtime_example.html"}

## Twee Code

```twee
:: StoryTitle
Date and Time in Snowman

:: Start
The current time (in milliseconds since January 1, 1970 00:00:00 UTC) is <%= Date.now() %>

<%
  window.setup = {};
  window.setup.newDate = new Date();
%>
The current month is <%= setup.newDate.getMonth() %>.

The current day is <%= setup.newDate.getDay() %>.

The current hour is <%= setup.newDate.getHours() %>.

The current minute is <%= setup.newDate.getMinutes() %>.

The current fullyear is <%= setup.newDate.getFullYear() %>.

<% window.setup.originalDate = new Date("October 20, 2018") %>
It has been <%=  Date.now() - setup.originalDate%> milliseconds since October 20, 2018.
```

[Twee Download](snowman_dateandtime_twee.txt){ target="_top" download="snowman_dateandtime_twee.txt"}
