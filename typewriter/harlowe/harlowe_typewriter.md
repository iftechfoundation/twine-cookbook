# "Typewriter Effect": Harlowe (v2.0)

## Summary

"Typewriter Effect" demonstrates how to create a delayed character-by-character effect. In Harlowe, this is achieved using the *[(live:)](https://twine2.neocities.org/#macro_live)* macro for delayed showing and the *[(substring:)](https://twine2.neocities.org/#macro_substring)* macro for selecting a single chracter position.

## Live Example

<section>
<iframe src="harlowe_typewriter_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_typewriter_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Typewriter Effect in Harlowe

:: Start
<!-- Set the text to show -->
(set: $textToShow to "Hello, world!")
<!-- Display (call) the Typewriter passage -->
(display: "Typewriter")

:: Typewriter
{
	<!-- Create an empty array -->
	(set: $textArray to (a:) )
	
	<!-- Convert the string into an array -->
	(for: each _item, ...$textToShow)[
		(set: $textArray to it + (a: _item) )
	]
	
	<!-- Harlowe arrays start at index 1 -->
	(set: $textArrayLength to 1)
	
	<!-- Set a delay of 1 second per loop -->
	(live: 1s)[
		
		<!-- Test if textArrayLength is length of textArray yet -->
		(if: $textArrayLength >= $textArray's length)[
			<!-- Stop the looping and show textToShow -->
			(stop:)
			$textToShow
		]
		(else:)[
			<!-- Show substring of textToShow -->
			(substring: $textToShow, 1, $textArrayLength)
			
			<!-- Update the index to next value -->
			(set: $textArrayLength to it + 1)
		]
	]
}

```

Download: <a href="harlowe_typewriter_twee.txt" target="_blank">Twee Code</a>

