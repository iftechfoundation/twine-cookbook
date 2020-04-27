# "Timed Progress Bars": SugarCube (v2.18)

## Summary

"Timed Progress Bars" uses the **[Macro.Add()](http://www.motoslave.net/sugarcube/2/docs/api-macro.html#macro-api)** function in SugarCube to introduce a new macro. Using jQuery within the definition, the new macro records arguments passed to it and creates outer and inner `<div>` elements with classes defined in the Story Stylesheet. Using a combination of **[setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval)** and **[setTimeout()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)**, a timer is created based on the argument passed to the macro. The length and color of an inner `<div>` element is adjusted based on the remaining time each loop.

When the timer runs out, the *payload* of the macro is run and the length of the inner `<div>` element is reduced to 0.

## Live Example

<section>
<iframe src="sugarcube_timed_progress_bars_example.html" height=400 width=90%></iframe>

Download: <a href="sugarcube_timed_progress_bars_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```twee
:: StoryTitle
Timed Progress Bars in SugarCube

:: UserScript[script]
/*
		Macro: timedprogressbar
		
		Description: Show a dynamically-created "progress bar" 
		that changes colors as its timer runs down.
		
		Original design: Akjosch (https://github.com/Akjosch)
		
		Arguments:
			[0]: The time to run in seconds
			[1]: The length of the progress bar in CSS units (px, em, or %)
*/
Macro.add("timedprogressbar", {
	isAsync : true,
	tags: null,
	handler: function() {
		// Filter the payload for newlines and save it for later execution
		var payload = this.payload[0].contents.replace(/\n$/, '').trim();
		
		// Save or generate a default duration
		var duration = (Number(this.args[0]) || 60) * 1000;
		
		// Save or generate a width
		var width = this.args[1] || "100%";
		
		// Generate a unique hash
		var hash = Math.floor(Math.random() * 0x100000000).toString(16);
		
		//  Create an outer ID
		var outerId = "outer_" + hash;
		
		// Create an inner ID
		var innerId = "inner_" + hash;
		
		// Create an outer div, 
		// add an ID,
		// add a class,
		// change the CSS width, and
		// append to the output
		var progressbar = $("<div>")
		.attr("id", outerId)
		.addClass("progress-bar")
		.css('width', width)
		.appendTo(this.output);
		
		// Create an inner div, 
		// add an ID,
		// add a class,
		// change the CSS width, and
		// append to the progressbar
		var progressvalue = $("<div>")
		.attr("id", innerId)
		.addClass("progress-value")
		.css('width', "100%")
		.appendTo(progressbar);
		
		// Create a function to convert into hexadecimal
		var toHex = function(num) {
			var res = Math.round(Number(num)).toString(16);
			return (res.length === 1 ? "0" + res : res);
		};
		
		// Save a reference to possible payload content
		var functionToRun = this.createShadowWrapper(
			payload
				? function() { Wikifier.wikifyEval(payload); }
				: null
		);
		
		// Watch for the :passagedisplay event once
		jQuery(document).one(":passagedisplay", function() {
			
			// Get the current time
			var timeStarted = (new Date()).getTime();
			
			// Save a reference to the setInterval function
			var workFunction = setInterval(function() {
				
				// Check if the element is still 'connected'
				if(! progressbar.prop("isConnected") ) {
					
					// Navigated away from the passage
					clearInterval(workFunction);
					return;
				}
				
				// Figure out how much time has passed
				var timePassed = (new Date()).getTime() - timeStarted;
				
				// Check if the timer has run out
				if(timePassed >= duration) {
					
					// Reduce the inner width to 0
					progressvalue.css('width', "0");
					
					// Clear interval
					clearInterval(workFunction);
					
					// Run the inner function (if set)
					setTimeout(functionToRun, 40);
					return;
				}
				
				// Update the progress percentage
				var percentage = 100 - 100 * timePassed / duration;
				
				// Save the new color
				var color = "#"
					+ toHex(Math.min(255, 510 -  5.1 * percentage))
					+ toHex(Math.min(255, 5.1 * percentage)) + "00";
				
				// Update the background color of the inner div
				progressvalue.css("backgroundColor", color);
				
				// Update the inner div width
				progressvalue.css("width", (100 - 100 * timePassed / duration) + "%");
				
			}, 40);
			
		});
	},
});


:: UserStylesheet[stylesheet]
.progress-bar {
	position: relative;
	border: 1px solid #777;
	background: black;
	height: 1em;
}

.progress-value {
	position: absolute;
	top: 0;
	left: 0;
	height: 100%;
	background: #00ff00;
}



:: Start
<<timedprogressbar 5 20em>>
	<<run UI.alert("Too late!")>>
<</timedprogressbar>>

```

Download: <a href="sugarcube_timed_progress_bars_twee.txt" target="_blank">Twee Code</a>

## See Also

[Adding Functionality](../../addingfunctionality/sugarcube/sugarcube_adding_functionality.md)
