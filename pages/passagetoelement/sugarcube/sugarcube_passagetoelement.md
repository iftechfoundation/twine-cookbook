# "Render Passage to Element": SugarCube (v2.0.0)

## Summary

In SugarCube, the function **[setPageElement()](http://www.motoslave.net/sugarcube/2/docs/#functions-function-setpageelement)** renders the contents of a passage into an element based on its *id*.

The event ":passagedisplay" is used in this example to guarantee that the passage has been rendered before acting. Calling the function **setPageElement()** inside the [jQuery event listener](https://api.jquery.com/on/) then renders another passage into an existing element.

## Example

[Download](sugarcube_passagetoelement_example.html)

## Twee Code

```twee
:: StoryTitle
SugarCube: Render Passage to Element

:: Start
<div id="hudID"></div>
<<script>>
  // Wait for the passage to be displayed
  $(document).one(':passagedisplay', function (ev) {
    // Render the passage named HUD into the element with id of "hudID"
    setPageElement("hudID", "HUD");
  });
<</script>>

:: HUD
<h1>This is the heads-up display!</h1>

```

[Twee Download](sugarcube_passagetoelement_twee.txt)
