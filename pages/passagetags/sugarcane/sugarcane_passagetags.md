# "CSS and Passage Tags": Sugarcane (v1.4.2)

!!! Warning
    The following example is designed for Twine 1.4.2.

## Summary

This example shows how to use CSS selectors to selectively style different passages based on how they are tagged. In Sugarcane, the "data-tags" attribute can be used to create different sets of styles and apply them when shown.

## Example

[Download](sugarcane_passagetags_example.html){: target="_top" download="sugarcane_passagetags_example.html"}

## Twee Code

```twee
:: Start [grey]
This passage has a grey background and white text.

[[Second]]

:: Second [yellow]
This passage has a yellow background and black text.

:: StoryTitle
CSS and Passage Tags in Twine 1.4.2

:: Stylesheet [stylesheet]
[data-tags="grey"] {
  background: grey;
  color: white;
}

[data-tags="yellow"] {
  background: yellow;
  color: black;
}

:: StoryAuthor
Videlais

```

[Twee Download](sugarcane_passagetags_twee.txt){ target="_top" download="sugarcane_passagetags_twee.txt"}
