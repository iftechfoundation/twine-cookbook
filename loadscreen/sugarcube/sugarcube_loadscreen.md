# "Loading Screen": SugarCube (v2.18)

## Summary

"Loading Screen" demonstrates how the **[LockScreen.lock()](http://www.motoslave.net/sugarcube/2/docs/#loadscreen-api-method-lock)** and **[LockScreen.unlock()](http://www.motoslave.net/sugarcube/2/docs/#loadscreen-api-method-lock)** functions work in SugarCube. (This example also uses the **[setTimeout()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)** JavaScript function.)

## Live Example

<section>
<iframe src="sugarcube_loadscreen_example.html" height=400 width=90%></iframe>

Download: <a href="sugarcube_loadscreen_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Loading Screen in SugarCube

:: UserScript[script]
// Lock the screen and save the ID
var lockID = LoadScreen.lock();
	
// Pause for 5 second before unlocking the screen
setTimeout(function(){ 
		LoadScreen.unlock(lockID);
}, 5000);

:: Start
You can now see this after the long pause!

```

Download: <a href="sugarcube_loadscreen_twee.txt" target="_blank">Twee Code</a>
