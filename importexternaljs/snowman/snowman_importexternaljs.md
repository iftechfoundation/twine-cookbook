# "Importing External JavaScript": Snowman (v1.3.0)

## Summary

"Importing External JavaScript" demostrates how to import an externally stored JavaScript library, [jQuery UI](https://jqueryui.com/).

This example uses the built-in jQuery [$.getScript(url) function](https://api.jquery.com/jquery.getscript/) to load the library and demonstrates a short example of how to use it.

<div class="alertbox information"><strong>Note:</strong> The successful loading of an external JavaScript file or library commonly producess no visual output. The code within the example passage is not required for the succesful loading of an external file or library.</div>


## Live Example

<section>
<iframe src="snowman_importexternaljs_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_importexternaljs_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Snowman: Importing External JavaScript


:: UserScript [script]
/* import jQuery UI library. */
$(function () {
	$.getScript("https://ajax.googleapis.com/ajax/libs/jqueryui/1.12.1/jquery-ui.min.js",
		function (data, textStatus, jqxhr) {
			console.log('jquery ui file loaded');
		}
	);
});


:: Start
<p>Click on the grey box below to see it bounce.</p>
<div id="box" style="width: 100px; height: 100px; background: #ccc;"></div>
 
<script>
$("#box").click(function () {
  $("#box").toggle("bounce", {times: 3}, "slow");
});
</script>


```

Download: <a href="snowman_importexternaljs_twee.txt" target="_blank">Twee Code</a>

