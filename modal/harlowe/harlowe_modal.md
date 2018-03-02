# "Modal (Pop-up Window)": Harlowe (v2.0)

## Summary
This example creates a re-usable [modal window](https://en.wikipedia.org/wiki/Modal_window). It can be opened using the combination of [*(link-repeat:)*](https://twine2.neocities.org/#macro_link-repeat) and [*(replace:)*](https://twine2.neocities.org/#macro_replace) to create the window in an existing hook, and be 'closed' using the same macros to remove the window. CSS rules are applied with [*(css:)*](https://twine2.neocities.org/#macro_css) to style the modal, and to change an enclosing hook into a "dimmer" which obscures the rest of the page.

## Live Example

<section>
<iframe src="harlowe_modal_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_modal_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Harlowe: Modal

:: Header[header]
|modalhooks>[]

:: Modal code
(replace: ?modalhooks)[{
  (css:"
	position: fixed;
	display:block;
	z-index: 1;
	left: 0;
	top: 0;
	width: 100%; /* Full width */
	height: 100%; /* Full height */
	overflow: auto; /* Enable scroll if needed */
	background-color: rgba(0,0,0,0.4);
  ")[
	(css:"
	  display:block;
	  margin: 15% auto;
	  padding: 20px;
	  width: 80%;
	  border: 1px solid white;
	")|modal>[
	  (css:"float:right")+(link-repeat:"×")[(replace: ?modalhooks)[]]
	]
  ]
}]

:: Start
(link-repeat:"Open Modal!")[(display:"Modal code")(append:?modal)[Some text in the modal...]]
```

Download: <a href="harlowe_modal_twee.txt" target="_blank">Twee Code</a>
