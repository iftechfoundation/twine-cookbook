# "Importing External JavaScript": SugarCube (v2.18)

## Summary

"Importing External JavaScript" demostrates how to import an externally stored Javascript script.

It uses the SugarCube 2 <a href="http://www.motoslave.net/sugarcube/2/docs/functions.html#importscripts">importScripts(urls) function</a> to load and integrate the script file's contents.

> **NOTE:**
>
> The successful loading of an external Javascript script commonly producess no visual output, which presents a problem when trying to create a **visual** Live Example for a recipe. For that reason the following example demostrates how to load the [jQuery UI library](https://jqueryui.com/), and includes code within the **Start** passage which interactively applies a bounce effect to a square.
>
> The code within the **Start** passage **IS NOT** required for the succesful loading of an external Javascript script, nor should it be considered an example of the best way to implement said effect.


## Live Example

<section>
<iframe src="sugarcube_importexternaljs_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_importexternaljs_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
SugarCube: Importing External JavaScript


:: UserScript [script]
/* Import the jQuery UI library. */
importScripts("https://ajax.googleapis.com/ajax/libs/jqueryui/1.12.1/jquery-ui.min.js");


:: Start
<p>Click on the grey box below to see it bounce.</p>
<div id="box" style="width: 100px; height: 100px; background: #ccc;"></div>
 
<<script>>
$(document).one(':passagerender', function (ev) {
	$(ev.content)
		.find("#box")
		.click(function () {
			$("#box").toggle("bounce", {times: 3}, "slow");
		});
});
<</script>>


```

Download: <a href="sugarcube_importexternaljs_twee.txt" target="_blank">Twee Code</a>

