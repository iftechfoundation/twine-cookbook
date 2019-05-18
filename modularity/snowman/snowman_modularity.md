# "Modularity": Snowman (v1.3.0)

## Summary

In programming terminology, modularity refers to dividing software into different sections related to their purpose or to better organize the whole. In Snowman, this technique can be used through the [*window.story.render()*](https://twinery.org/wiki/snowman:window-story:render) function to print the contents of one passage in another. Parts of a story can often be re-used in this way.

## Twee Code

```
:: StoryTitle
Modularity in Snowman

:: Start
<%
	s.lineOne = "Give us a verse";
	s.lineTwo = "Drop some knowledge";
%>

<%= window.story.render("showLineOne") %>
<%= window.story.render("showLineTwo") %>


:: showLineOne
<%= s.lineOne %>

:: showLineTwo
<%= s.lineTwo %>
```
