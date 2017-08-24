#"Moving through a 'dungeon": Harlowe (v2.0)
*Contributed by <a href="https://github.com/videlais">@videlais</a>*

#Summary
"Moving through a 'dungeon'" uses the <a href="https://twine2.neocities.org/#macro_a">(array:)</a> macro to create a multidimensional array. Movement positions are then tracked through X and Y variables for a grid system. Each movement subtracts or adds to its cooresponding X or Y position and is compared to those same positions within the array. Different directions are shown if movement is possible in that direction.

A map of the array is created through using temporary variables and building a HTML table by iterating through the it and placing different symbols matching walls, movement spaces, and the player herself.

#Live Example
<section>
<iframe src="harlowe_dungeonmoving_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_dungeonmoving_example.html" target="_blank">Live Example</a>
</section>

#Twee Code
<section>
<iframe src="harlowe_dungeonmoving_twee.txt" height=400 width=90%></iframe>


Download: <a href="harlowe_dungeonmoving_twee.txt" target="_blank">Twee Code</a>
</section>
