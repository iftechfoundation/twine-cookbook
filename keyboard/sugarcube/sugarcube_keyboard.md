# "Keyboard": SugarCube (v2.18)

## Summary

"Keyboard" demostrates how to track [keyboard events](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent) (which key was pressed) and how to associate individual keys with activities within a story.

The code uses jQuery's [**on** function](http://api.jquery.com/on/) to monitor for all [**keyup** events](https://developer.mozilla.org/en-US/docs/Web/Events/keyup) (when a key is released).

Once a ''keyup'' event has occurred the developer has one of two choices for how to determine **which** key was released:

1. The event object's **keyCode** property<br>
   which is supported in effectively all web-browsers (both modern and legacy) but requires the developer to know the [decimal ASCII codes](http://www.asciichart.com/) for the keys that they are interested in.

2. The event object's **key** property<br>
   which is supported by most modern web-browsers.


## Live Example

<section>
<iframe src="sugarcube_keyboard_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_keyboard_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
SugarCube: Keyboard

:: UserScript[script]
(function () {
	$(document).on('keyup', function (ev) {
		/* the ev variable contains a keyup event object.
		 *
		 * ev.keyCode - contains the ASCII code of the key that was released, this property is supported in effectively all browsers.
		 * ev.key     - contains the key value of the key that was released, this property is supported by most modern browsers.
		 *
		 */


		/* the following shows an alert when the 'a' key is released. */
		if (ev.key === 'a') {
			UI.alert("the 'a' key was released.");
		}
	});
}());


:: Start
Press and release the ''a'' key to show an Alert dialog.

```

Download: <a href="sugarcube_keyboard_twee.txt" target="_blank">Twee Code</a>

