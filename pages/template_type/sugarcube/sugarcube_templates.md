# "Templates": SugarCube (v2.29)

## Summary

Starting in SugarCube 2.29, [Templates](https://www.motoslave.net/sugarcube/2/docs/#template-api) can be used to create a new special type of value that looks like a variable but acts like a macro. Templates follow the same rules as variables (limited to letters, numbers, and the underscore), but they start with the question mark, `?`, and can contain the hyphen in their name.

> **Note:** Templates are added using the Template API in SugarCube. They must be defined *before* they appear in a story.

This example also uses the [`StoryInit` special passage name](https://www.motoslave.net/sugarcube/2/docs/#special-passage-storyinit) with the [`<<script>>` macro](https://www.motoslave.net/sugarcube/2/docs/#macros-macro-script) to create a template before the first passage is shown.

## Example

[Download](sugarcube_templates_example.html){: target="_top" download="sugarcube_templates_example.html"}

## Twee Code

```twee
:: StoryTitle
SugarCube: Templates

:: Start
You see a pirate before you.

Pirate: "?pirate"

:: StoryInit
<<script>>
Template.add('pirate', function () {
  return "Hello, me hardy!";
});
<</script>>

```

[Twee Download](sugarcube_templates_twee.txt){ target="_top" download="sugarcube_templates_twee.txt"}
