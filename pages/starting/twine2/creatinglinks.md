# Creating Links

The easiest way to [connect to passages](../../terms/terms_passages.md#connecting-passages) is through a *link*.

## Passage Links

By default, passage links are one-way. Navigating the link means moving away from one to another.

### Link to Another Passage named "Link to another passage"

```twee
[[Link to another passage]]
```

### Link to Another Passage Named "Different Passage"

The pipe, "`|`", can be used to rename a link from its original to some other name for the same purpose.

```twee
[[Link to another passage|Different Passage]]
```

### Link to Another Passage Named "Different Passage" Using Routing

Starting in Twine 2, to route links, arrows, "->" or "<-", can be used to *point* to the destination of the link.

```twee
[[Link to another passage->Different Passage]]
```

```twee
[[Different Passage<-Link to another passage]]
```

## Story Format Additions

SugarCube adds to the [existing passage link syntax](https://www.motoslave.net/sugarcube/2/docs/#markup-link), allowing TwineScript and other things within links.
