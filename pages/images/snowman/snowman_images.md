# "Images": Snowman (v1.3.0)

## Summary

When using Snowman, images can be displayed through the [image HTML element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) and **[url()](https://developer.mozilla.org/en-US/docs/Web/CSS/url)** CSS data type when encoded as Base64.

When using an image element, its source is either absolutely or relatively located. An absolute reference starts with HTTP or another protocol; a relative reference describes the location of the image in relation to the webpage.

Because images are external resources, they need to be included with the webpage as Base64-encoded or in another location. While Base64-encoded images can be embedded in a webpage, it also increases its overall size. External images require additional hosting and are included through their reference in CSS (URL) data type or image (SRC) attribute.

## Example

[Download](snowman_images_example.html){: target="_top" download="snowman_images_example.html"}

## Twee Code

```twee
:: StoryTitle
Images in Snowman

:: UserStylesheet[stylesheet]
.base64image {
  width: 256px;
  height: 256px;
  /* Base64 image truncated for example */
  /* See Twee file for full version. */
  background-image: url('data:image/png;base64...');
}

:: Start
This is an image element:

<img src="https://twinery.org/homepage/img/logo.svg" width="256" height="256">

This is a Base64-encoded CSS image background:

<div class="base64image"></div>

```

[Twee Download](snowman_images_twee.txt){ target="_top" download="snowman_images_twee.txt"}
