# "CSS and Passage Tags": Harlowe (v2.0)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

<div class="alert warning"><strong>Note:</strong> The following recipe is designed for use in Harlowe 2.x and later</div>

## Summary

This example shows how to use CSS selectors to selectively style different passages based on how they are tagged. In Harlowe, the "tags" attribute can be used to create different sets of styles and apply them when shown.

## Live Example

<section>
<iframe src="harlowe_passagetags_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_passagetags_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
CSS and Passage Tags in Harlowe

:: UserStylesheet[stylesheet]
[tags="grey"] {
    background: grey;
}

[tags="yellow"] {
    background: yellow;
  	color: black;
}

:: Start[grey]
This passage has a grey background and (default) white text.
[[Second]]

:: Second[yellow]
This passage has a yellow background and black text.


```

Download: <a href="harlowe_passagetags_twee.txt" target="_blank">Twee Code</a>

