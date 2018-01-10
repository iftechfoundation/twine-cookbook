# "Cycling Choices": Snowman (v1.3.0)

## Summary

"Cycling Choices" demostrates how to create a 'cycling' effect of different choices through clicking on them.

Starting with iterating over all elements with the class 'cycle', each element's 'choices' and 'selection' attribute values are saved as global variables not expected to change during the story. Next, through using jQuery, a *.click()* trigger is set for all elements with the class 'cycle'.

When triggered, the global values of 'choices' and 'selection' for the element are retrieved and the 'selection' updated. The 'text' of the element is set to the selection index of the 'choices' array.

Finally, the global variables are updated according to the element's 'id' for later access and to prevent changes to the history of the story potentially affecting saved values.

## Live Example

<section>
<iframe src="snowman_cycling_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_cycling_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Cycling Choices in Snowman

:: UserScript[script]
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
		window.twine[id].selection = selection;
  		
	});
	
	$('.cycle').click(function(){
		
		// Save the 'id'
		var id = $(this).attr('id');
		
		// Retrieve the global 'choices'
		var choices = window.twine[id].choices;
		
		// Retrieve the global 'selection'
		var selection = window.twine[id].selection;
		
		// Update the 'selection' number
		selection++;
		
		// Check if 'selection' is greater than length of choices
		if(selection >= choices.length) {
			selection = 0;
		}
		
		// Update the 'selection' on the element
		$(this).attr("data-cycling-selection", selection);
		
		// Update the text of the element with the choice
		$(this).text(choices[selection]);
	
		// Update the global values of 'choices' and 'selection'
		window.twine[id].choices = choices; 
		window.twine[id].selection = selection;
	
	});
	
});

:: Start
<a href='javascript:void(0)' id='cycleOne' class='cycle' data-cycling-choices='["One", "Two", "Three"]' data-cycling-selection=0>One</a>

[[Submit|Results]]

:: Results
<%= window.twine["cycleOne"].choices[window.twine["cycleOne"].selection] %>

```

Download: <a href="snowman_cycling_twee.txt" target="_blank">Twee Code</a>

