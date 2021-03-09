# "Headers and Footers": Snowman (v1.3)

## Summary

"Headers and Footers" demonstrates the use of the **window.story.render()** function to return the HTML contents of another passage. Combined with [Underscore template functionality](http://underscorejs.org/#template), the content of passages can be "displayed" in others. Because Snowman does not have pre-defined 'header' or 'footer' functionality, using these two different methods together can create the same result. However, the code would need to be included on any additional passages to continue the effect.

## Example

[Download](snowman_headersandfooters_example.html){: target="_top" download="snowman_headersandfooters_example.html"}

## Twee Code

```twee
:: StoryTitle
Snowman: Headers and Footers

:: Start
<%= window.story.render("Header") %>

This content is between the header and the footer.

<%= window.story.render("Footer") %>

:: Header
This is the header!

:: Footer
This is the footer!
```

[Twee Download](snowman_headersandfooters_twee.txt){ target="_top" download="snowman_headersandfooters_twee.txt"}

## See Also

[Passage Events](../../passageevents/snowman/snowman_passage_events.md)
