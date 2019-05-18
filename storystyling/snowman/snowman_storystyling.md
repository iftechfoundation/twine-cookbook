# "Variable Story Styling": Snowman (v1.3.0)

## Summary

"Variable Story Styling" demonstrates how to use the *[toggleClass()](http://api.jquery.com/toggleclass/)* jQuery function to switch between two pre-defined style rulesets. Used with the “body” selector, the entire page is selected and the classes toggled when the function is called.

## Twee Code

```
:: StoryTitle
Variable Story Styling in Snowman

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
<%
	s.styling = "green";
	$("body").toggleClass(s.styling)
%>
[[Next Passage]]

:: Next Passage
This text is white on a black background.
<%
	s.styling = "white";
	$("body").toggleClass(s.styling);
%>

```
