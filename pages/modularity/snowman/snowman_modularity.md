# "Modularity": Snowman (v1.3.0)

## Summary

In programming terminology, modularity refers to dividing software into different sections related to their purpose or to better organize the whole. In Snowman, this technique can be used through the **[window.story.render()](https://videlais.github.io/snowman/#/1/window_story/functions/render)** function to print the contents of one passage in another. Parts of a story can often be re-used in this way.

## Example

[Download](snowman_modularity_example.html){: target="_top" download="snowman_modularity_example.html"}

## Twee Code

```twee
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

[Twee Download](snowman_modularity_twee.txt){ target="_top" download="snowman_modularity_twee.txt"}
