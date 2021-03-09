# "CSS and Passage Tags": Harlowe (v2.0)

!!! Warning
    The following example is designed for use in Harlowe 2.x and later

## Summary

This example shows how to use CSS selectors to selectively style different passages based on how they are tagged. In Harlowe, the "tags" attribute can be used to create different sets of styles and apply them when shown.

## Example

[Download](harlowe_passagetags_example.html){: target="_top" download="harlowe_passagetags_example.html"}

## Twee Code

```twee
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

[Twee Download](harlowe_passagetags_twee.txt){ target="_top" download="harlowe_passagetags_twee.txt"}
