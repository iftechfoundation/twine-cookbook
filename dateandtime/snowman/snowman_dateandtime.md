# "Date and Time": Snowman (v1.3)

## Summary

"Date and Time" demonstrates how to use the JavaScirpt *[Date() ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)* functionality in Snowman.

## Live Example

<section>
<iframe src="snowman_dateandtime_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_dateandtime_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
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
Download: <a href="snowman_dateandtime_twee.txt" target="_blank">Twee Code</a>
