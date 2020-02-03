# "Modularity": Snowman (v1.3.0)

## Summary

In programming terminology, modularity refers to dividing software into different sections related to their purpose or to better organize the whole. In Snowman, this technique can be used through the **[window.story.render()](https://videlais.github.io/snowman/1/window_story/functions/render.html)** function to print the contents of one passage in another. Parts of a story can often be re-used in this way.

## Live Example

<section>
<iframe src="snowman_modularity_example.html" height=400 width=90%></iframe>

Download: <a href="snowman_modularity_example.html" target="_blank">Live Example</a>
</section>

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

Download: <a href="snowman_modularity_twee.txt" target="_blank">Twee Code</a>

