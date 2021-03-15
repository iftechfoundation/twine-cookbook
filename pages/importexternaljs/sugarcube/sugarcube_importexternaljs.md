# "Importing External JavaScript": SugarCube (v2.18)

!!! Information
    The successful loading of an external JavaScript file or library commonly produces no visual output. The code within the example passage is not required for the successful loading of an external file or library.

## Summary

"Importing External JavaScript" demonstrates how to import an externally stored JavaScript library, [jQuery UI](https://jqueryui.com/).

This example uses the SugarCube **[importScripts()](http://www.motoslave.net/sugarcube/2/docs/functions.html#importscripts)** function to load and integrate the script file's contents.

## Example

[Download](sugarcube_importexternaljs_example.html){: target="_top" download="sugarcube_importexternaljs_example.html"}

## Twee Code

```twee
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

[Twee Download](sugarcube_importexternaljs_twee.txt){ target="_top" download="sugarcube_importexternaljs_twee.txt"}
