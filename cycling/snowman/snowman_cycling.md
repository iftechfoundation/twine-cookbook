# "Cycling Choices": Snowman (v1.3.0)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary

"Cycling Choices" demostrates how to create a 'cycling' effect of different choices through clicking on them.

Starting with iterating over all elements with the class 'cycle,' each elements's 'choices' and 'selection' attribute values are saved as global variables. Next, through using jQuery, a *.click()* trigger is set for all elements with the class 'cycle'.

When triggered, the 'data-cycling-choices' attribute is converted to an array. The 'data-cycling-selection' attribute is retrieved, increased, and updated. The 'text' of the element is set to the selection index of the 'choices' array.

Finally, the global variables are updated according to the element's 'id' for later access.


## Live Example

<section>
<iframe src="snowman_cycling_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_cycling_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Cycling Choices in Snowman

:: Start
<a href='javascript:void(0)' id='cycleOne' class='cycle' data-cycling-choices='["One", "Two", "Three"]' data-cycling-selection=0>One</a>

<%
$(function() {
	// Create a global object
	window.twine = {};
	
	// Iterate through all elements with the class 'cycle'
	//  For each, save the current 'choices' and 'selection'
	//  (This sets all the 'default' values.)
	$('.cycle').each(function() {
		
		// Create a global object for each 'id'
		var id = $(this).attr('id');
		window.twine[id] = {};
		
		// Save the current 'choices' for each
		var choices = JSON.parse($(this).attr("data-cycling-choices"));
		window.twine[id].choices = choices; 
		
		// Save the current 'selection' for each
		var selection = $(this).attr("data-cycling-selection");
		window.twine[id].selection = choices[selection];
  		
	});
	
	$('.cycle').click(function(){
		// Convert 'choices' attribute into array
		var choices = JSON.parse($(this).attr("data-cycling-choices"));
	
		// Check if 'choices' has values
		if (typeof(choices) === typeof(undefined)) {
  			return;
		}
	
		// Retrieve and update 'selection'
		var selection = $(this).attr("data-cycling-selection");
		selection++;
		
		// Check if 'selection' is greater than length of choices
		if(selection >= choices.length) {
			selection = 0;
		}
		
		// Update the attribute and text of the element
		$(this).attr("data-cycling-selection", selection);
		$(this).text(choices[selection]);
	
		// Save the 'id'
		var id = $(this).attr('id');
	
		// Reset the global values of 'choices' and 'selection'
		window.twine[id].choices = choices; 
		window.twine[id].selection = choices[selection];
	
	});
});

%>

[[Submit|Results]]

:: Results
<%= window.twine["cycleOne"].selection %>

```

Download: <a href="snowman_cycling_twee.txt" target="_blank">Twee Code</a>

