# "CSS and Passage Tags": SugarCube (v2.18)

## Summary

This example shows how to use CSS selectors to style different passages based on how they are tagged. [In SugarCube](http://www.motoslave.net/sugarcube/2/docs/css.html), the tag name is applied to both the *body* and the passage shown. To style different parts, use either the *body* selector or a combination of 'passage' and the tag name.

SugarCube 2.x and later also applies a "data-tags" attribute to the html, body, and .passage elements. These can also be used to style the page at different levels.

## Live Example

<section>
<iframe src="sugarcube_passagetags_example.html" height=400 width=90%></iframe>

Download: <a href="sugarcube_passagetags_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
CSS and Passage Tags in SugarCube

:: UserStylesheet[stylesheet]
/* Style the entire body when showing passage tagged with grey */
body.grey {
  color: green;
}

/* Style only the inner part of the passage tagged with "grey" */
.passage.grey { 
  background: grey;
}

/* Style only the inner part of the passage tagged with "yellow" */
.passage.yellow { 
  background: yellow;
  color: black;
}

:: Start[grey]
This passage has a grey background and green text.
[[Second]]

:: Second[yellow]
This passage has a yellow background and black text.

```

Download: <a href="sugarcube_passagetags_twee.txt" target="_blank">Twee Code</a>

