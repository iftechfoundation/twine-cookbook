# "Static Healthbars": Chapbook (v1.0.0)

## Summary

"Static Healthbars" demonstrates how to write HTML elements using JavaScript in Chapbook. Through the [`[JavaScript]`](https://klembot.github.io/chapbook/guide/advanced/using-javascript-in-passages.html) can be included in a passage. Chapbook also provides the **engine.state.get()** and **engine.state.set()** functions for getting and setting story variables.

Using these and the **write()** function, dynamic values can be created, accessed, and combined to produce static "healthbars" using the `<progress>` and `<meter>` HTML elements.

## Live Example

<section>
<iframe src="chapbook_statichealthbars_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_statichealthbars_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Chapbook: Static Healthbars

:: Start
[JavaScript]
	// Create a global variable, health
	engine.state.set('health', 80);
	
	// Get the current value of 'health'
	let health = engine.state.get('health');
	
	// Write description
	write("Show a healthbar using a Progress element:<br>");
	
	// Write the progress element with dynamic value
	write('<progress value="' + health + '" max="100"></progress><br>');
	
	// Write description
	write("Show a healthbar using a Meter element:<br>");
	
	// Write the meter element with dynamic value
	write('<meter value="' + health + '" min="0" max="100"></meter>');

```

Download: <a href="chapbook_statichealthbars_twee.txt" target="_blank">Twee Code</a>
