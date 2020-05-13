# Images

It is said that the most important tag in early World Wide Web history was `<img>`. With it, web pages could finally stop looking like structured documents and start looking like anything they wanted to look like. This was the Web's defining advantage over its competitors. In that sense, images and hypertext are intimately intwined, and in Twine their relevance is not diminished.

## Importing images

Images can serve many purposes in a story or game - passage illustrations, page backgrounds, interstitial GIF animations, a title logo, and so forth. Given their vital importance, Twine enables incorporating images into a project's story file, as separate "passages" alongside text. Images stored in the story file will be embedded inside a finished story's built HTML - guaranteeing that the images will *always* be visible in the story, even if the HTML file is uploaded to a site or service.

An image asset can be added using the "Import Image" menu items in the Story menu, or by dragging and dropping an image file into the Story Map.

> **Note:** In Twine 1.4.2 or above, the program will ask, when a passage is closed, if it can automatically import the external images used in it - the images referred to by URLs.

Image assets appear in as passages with teal titles.

### A note about formats

Since Twine games run in a web browser, any format that the browser supports can be displayed. However, the Twine development program only supports the following formats as imported image assets: PNG, GIF, JPEG, WebP and SVG. Furthermore, due to limitations in wxPython, WebP and SVG images will *not* display in the Story Map (but will remain usable in the browser).

## Usage

Once imported, an image can be referred to it by its name using this syntax:

```twee
[[img[*image name*]]
```

Making an image that is also a link to another passage:

```twee
[img[*image name*][*Passage name*]]
```

Putting the `<` or `>` symbols in front of 'img', it will be floated to the left or right, insetting it in the passage text:

```twee
[<img[*image name*]]
[>img[*image name*]]
```

You can add "alt text" (title text) to the image like so:

```twee
[img[*alt text*|*image name*]]
```

And, you can refer to external image URLs with this syntax, too.

```twee
[img[*http://example.com/icon.png*]]
```

This syntax is mostly a shorthand for the HTML `<img\>` element. If you need to customize the image further (for instance, by adding a class or style attribute) then you can fall back to `<img\>` - but note that you can't refer to imported image assets with it:

```html
<img src="image URL"\>
```
