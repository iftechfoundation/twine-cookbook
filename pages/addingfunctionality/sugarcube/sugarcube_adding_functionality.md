# "Adding Functionality": SugarCube (v2.18)

## Summary

In SugarCube, additional functionality can be added through the *[Macro.add()](http://www.motoslave.net/sugarcube/2/docs/api-macro.html#macro-api)* function.

In this example, the *[Date()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)* JavaScript function is used to get the current time. This is saved to *payload.contents*, and the *[jQuery.wiki()](http://www.motoslave.net/sugarcube/2/docs/object-methods.html#jquery-jqueryprotowiki)* function is used to convert and append it to the current passage.

## Example

[Download](sugarcube_adding_functionality_example.html){ target="_top" download="sugarcube_adding_functionality_example.html"}

## Twee Code

```twee
:: StoryTitle
Adding Functionality in SugarCube

:: UserScript[script]
Macro.add("currenttime", {
  tags: null,
  handler: function() {
    // Try the following code and catch any errors
    try {
      // Get the current time and save it to the payload
      this.payload.contents = new Date();

      // Wikify (and append) the current payload contents
      jQuery(this.output).wiki(this.payload.contents);

    } catch (ex) {
      // Return any errors
      return this.error("Error: " + ex.message);
    }
  }
});

:: Start
<<currenttime>><</currenttime>>

```

[Twee Download](sugarcube_adding_functionality_twee.txt){ target="_top" download="sugarcube_adding_functionality_twee.txt"}
