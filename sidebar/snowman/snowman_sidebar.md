# "Sidebar": Snowman (v1.3.0)

## Summary

Snowman does not have a built-in sidebar. However, one can be created through using CSS and including a DIV element on every passage. Through using the [*window.story.render()*](https://twinery.org/wiki/snowman:window-story:render) function and [Underscore template functionality](http://underscorejs.org/#template), the contents of the "Sidebar" passage can be included in the created sidebar.

## Live Example

<section>
<iframe src="snowman_sidebar_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_sidebar_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Sidebar in Snowman

:: UserStylesheet[stylesheet]
#sidebar {
	background-color: #222;
    color: white;
	border-right: 1px solid #444;
	position: fixed;
	top: 0;
	right: 0;
	width: 20%;
	height: 100%;
	margin: 0;
	padding: 0.5em; 
}

:: Start
<div id="sidebar"><%= window.story.render("Sidebar") %></div>
[[Another passage]]

:: Sidebar
This is the sidebar!

:: Another passage
<div id="sidebar"><%= window.story.render("Sidebar") %></div>
[[Start]] 


```

Download: <a href="snowman_sidebar_twee.txt" target="_blank">Twee Code</a>

