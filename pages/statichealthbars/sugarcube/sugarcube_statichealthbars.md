# "Static Healthbars": SugarCube (v2.18)

## Summary

"Static Healthbars" demonstrates how to write HTML elements using variable values. In this example, [Attribute Directive](http://www.motoslave.net/sugarcube/2/docs/#markup-html-attribute-directive) markup is used to inject the current value of the *$heath* story variable into the `<progress>` and `<meter>` elements.

## Live Example

<section>
<iframe src="sugarcube_statichealthbars_example.html" height=400 width=90%></iframe>

Download: <a href="sugarcube_statichealthbars_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```twee
:: StoryTitle
Static Healthbars for SugarCube

:: Start
<<set $health to 80>>

Show a healthbar using a Progress element:
<progress @value="$health" max="100"></progress>

Show a healthbar using a Meter element:
<meter @value="$health" min="0" max="100"></meter>


```

Download: <a href="sugarcube_statichealthbars_twee.txt" target="_blank">Twee Code</a>
