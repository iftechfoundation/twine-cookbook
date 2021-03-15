# "Importing External JavaScript": Snowman (v1.3.0)

!!! Information
    The successful loading of an external JavaScript file or library commonly produces no visual output. The code within the example passage is not required for the successful loading of an external file or library.

## Summary

"Importing External JavaScript" demonstrates how to import an externally stored JavaScript library, [jQuery UI](https://jqueryui.com/).

This example uses the built-in jQuery **[$.getScript()](https://api.jquery.com/jquery.getscript/)** function to load the library and demonstrates a short example of how to use it.

## Example

[Download](snowman_importexternaljs_example.html){: target="_top" download="snowman_importexternaljs_example.html"}

## Twee Code

```twee
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

[Twee Download](snowman_importexternaljs_twee.txt){ target="_top" download="snowman_importexternaljs_twee.txt"}
