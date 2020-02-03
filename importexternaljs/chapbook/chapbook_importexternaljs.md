# "Importing External JavaScript": Chapbook (v1.0.0)

<div class="alertbox information"><strong>Note:</strong>This example uses code from <a href="https://threejs.org/">Three.js</a>, a library for creating 3D graphics in the browser. It is include only for demonstrational purposes and its own documentation should be consulted to understand its functionality.</div>

## Summary

To include external JavaScript, it must first be loaded. This example uses code from the Mozilla Developer Network to [dynamically import scripts](https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement#Dynamically_importing_scripts). The example library loaded is Three.js.

Once loaded, a callback function is used to create a simple Three.js example and, if the browser supports it, shows a rotating 3D cube within the passage.

## Live Example

<section>
<iframe src="chapbook_importexternaljs_example.html" height=400 width=90%></iframe>


Download: <a href="chapbook_importexternaljs_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```

:: StoryTitle
Chapbook: Importing External JS

:: UserScript[script]
// The following code is used from MDN for
// dynamically importing scripts
// https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement#Dynamically_importing_scripts

window.setup = {};

setup.loadError = function(oError) {
  throw new URIError("The script " + oError.target.src + " didn't load correctly.");
};

setup.loadScript = function(url, onloadFunction) {
  var newScript = document.createElement("script");
  newScript.onerror = setup.loadError;
  if (onloadFunction) { newScript.onload = onloadFunction; }
  document.head.appendChild(newScript);
	newScript.async = true;
  newScript.src = url;
};


:: Start
<div id="drawArea"></div>
[JavaScript]
setup.loadScript("https://ajax.googleapis.com/ajax/libs/threejs/r84/three.min.js", function() {
	var scene = new THREE.Scene();
	var camera = new THREE.PerspectiveCamera( 
		75, 
		1,
		0.1,
		1000 );

	var renderer = new THREE.WebGLRenderer();
	renderer.setSize( 250, 250 );
	document.getElementById("drawArea").appendChild( renderer.domElement );

	var geometry = new THREE.BoxGeometry( 1, 1, 1 );
	var material = new THREE.MeshBasicMaterial( { color: 0x00ff00 } );
	var cube = new THREE.Mesh( geometry, material );
	scene.add( cube );

	camera.position.z = 5;

	var animate = function () {
		requestAnimationFrame( animate );

		cube.rotation.x += 0.01;
		cube.rotation.y += 0.01;

		renderer.render( scene, camera );
	};

	animate();
	
});

[continued]

```

Download: <a href="chapbook_importexternaljs_twee.txt" target="_blank">Twee Code</a>
