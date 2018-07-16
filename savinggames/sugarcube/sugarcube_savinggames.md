# "Saving Games": SugarCube (v2.18)

## Summary

SugarCube provides built-in functionality for saving, viewing, and deleting game saves through its sidebar. However, the [Save API](http://www.motoslave.net/sugarcube/2/docs/api-save.html) also provides programmable access for re-creating this for users through functions like [*Save.slots.has()*](http://www.motoslave.net/sugarcube/2/docs/api-save.html#slots-has), [*Save.slots.save()*](http://www.motoslave.net/sugarcube/2/docs/api-save.html#slots-save), and [*Save.slots.load()*](http://www.motoslave.net/sugarcube/2/docs/api-save.html#slots-load).

This example also demonstrates the use of the [*State.variables*](http://www.motoslave.net/sugarcube/2/docs/api-state.html#state-api-getter-variables) object to access variables in JavaScript and use them in TwineScript.

## Live Example

<section>
<iframe src="sugarcube_savinggames_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_savinggames_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Saving Games in SugarCube

:: Start
<<script>>
if (Save.slots.has(0)) {
	State.variables.slotA = true;
} else {
	State.variables.slotA = false;
}
<</script>>

<<if $slotA is true>>
	The first game slot exists! (This session was most likely reloaded from a game save.)
<</if>>

<<link "Save to the first slot?">>
	<<script>>
		if (Save.slots.ok()) { 
			Save.slots.save(0);
		}
	<</script>>
<</link>>

<<link "Load from the first slot?">>
	<<script>>
		if (Save.slots.has(0)) { 
			Save.slots.load(0);
		} 
	<</script>>
<</link>>

<<link "Delete first slot and restart story?">>
	<<script>>
		if (Save.slots.has(0)) { 
			Save.slots.delete(0);
			Engine.restart();
		} 
	<</script>>
<</link>>
```

Download: <a href="sugarcube_savinggames_twee.txt" target="_blank">Twee Code</a>
