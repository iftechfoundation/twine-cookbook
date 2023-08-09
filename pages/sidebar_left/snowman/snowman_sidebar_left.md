# "Left Sidebar": Snowman (v1.3.0)

## Summary

Snowman does not have a built-in sidebar, but one can be created using JavaScript, [jQuery](http://api.jquery.com/), and CSS.

The **[createElement()](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)** function is used to create a new DIV element into which the generated output of the Sidebar passage will later be added. This new DIV is assigned an ID of "sidebar" using the **[attr()](http://api.jquery.com/attr/#attr2)** function and then inserted into the story's Document Object Model (DOM) using the **[insertBefore()](http://api.jquery.com/insertbefore/)** function.

Snowman triggers a "showpassage:after" event after each passage is shown. The **[on()](http://api.jquery.com/on/)** function can be used to monitor for this event. Once it has occurred, a combination of the **[html()](http://api.jquery.com/html/)** and **[window.story.render()](https://videlais.github.io/snowman/#/1/window_story/functions/render)** functions can be used to display the dynamic contents of the Sidebar passage within the "sidebar" DIV element.

## Example

[Download](snowman_sidebar_left_example.html){: target="_top" download="snowman_sidebar_left_example.html"}

## Twee Code

```twee
:: StoryTitle
Left Sidebar in Snowman


:: UserScript [script]
/*
  Create the element to display the contents of the Sidebar passage in.
*/
$(document.createElement('div'))
  .attr('id', 'sidebar')
  .insertBefore('#passage');

/*
  Monitor for the event that is triggered after the current Passage has been shown.
*/
$(window).on('showpassage:after', function () {
  $('#sidebar').html(window.story.render("Sidebar"));
});


:: UserStylesheet[stylesheet]
#passage {
  margin-left: 20%;
}

#sidebar {
  position: fixed;
  top: 0;
  left: 0;
  width: 18%;
  height: 100%;
  margin: 0;
  padding: 0.5em;
  background-color: black;
    color: white;
}


:: Start
<% s.name = "Jane Doe"; s.location = "Work" %>
[[Another passage]]


:: Sidebar
Name: <%= s.name %><br>
Location: <%= s.location %>


:: Another passage
<% s.name = "John Smith"; s.location = "Shop" %>
[[Start]]
```

[Twee Download](snowman_sidebar_left_twee.txt){ target="_top" download="snowman_sidebar_left_twee.txt"}
