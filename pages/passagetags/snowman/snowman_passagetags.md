# "CSS and Passage Tags": Snowman (v1.3)

## Summary

This example shows how to use CSS selectors to style different passages. Snowman does not support tags in passages. However, the effect can be implemented through using [jQuery](https://jquery.com/) and the **[toggleClass()](http://api.jquery.com/toggleclass/)** function to switch between different pre-defined classes.

## Example

[Download](snowman_passagetags_example.html){: target="_top" download="snowman_passagetags_example.html"}

## Twee Code

```twee
:: StoryTitle
CSS and Passage Tags in Snowman

:: UserStylesheet[stylesheet]
.grey {
  background: grey;
  color: white;
}
.yellow {
  background: yellow;
  color: black;
}

:: Start[grey]
<% $("body").toggleClass("grey") %>
This passage has a grey background and white text.

[[Second]]

:: Second[yellow]
<% $("body").toggleClass("yellow") %>
This passage has a yellow background and black text.


```

[Twee Download](snowman_passagetags_twee.txt){ target="_top" download="snowman_passagetags_twee.txt"}
