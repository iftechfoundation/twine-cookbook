# "Variable Story Styling": Snowman (v1.3.0)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary

"Variable Story Styling" demonstrates how to use the *[toggleClass()](http://api.jquery.com/toggleclass/)* jQuery function to switch between two pre-defined style rulesets. Used with the “body” selector, the entire page is selected and the classes toggled when the function is called.

## Live Example

<section>
<iframe src="snowman_storystyling_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_storystyling_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Variable Story Styling in Snowman

:: UserScript[script]
window.styling = "green";


:: UserStylesheet[stylesheet]
.green {
	background: white;
  	color: green;
}
.white {
	background: black;
  	color: white;
}


:: Start
This text is green on a white background.
<% $("body").toggleClass(window.styling) %>
[[Next Passage]]

:: Next Passage
This text is white on a black background.
<% 
	window.styling = "white";
	$("body").toggleClass(window.styling);
%>

```

Download: <a href="snowman_storystyling_twee.txt" target="_blank">Twee Code</a>

