# Questions

## *How do I change the horizontal alignment of the text in all my passages in Sugarcane?*

This CSS example will change the text's horizontal alignment to the center:

```css
#passages { box-sizing:border-box; padding: 0 25% } .passage { text-align:center; }
```

Other options instead of "center" are "right" and "left."

## *How do I change the maximum width of passage text in Sugarcane?*

This CSS example sets the maximum width of passage text to 50%.

```css
.passage { max-width:50%; }
```

You can also use whole numbers (e.g. 300px will make the text container 300 pixels wide.)

## *How do I change the width of just the text that's centered (placed in `<center>` elements) in Sugarcane?*

This example sets the maximum width of passage text in `<center>` elements to 50%.

```css
.passage div { max-width:50%; }
```

You can also use whole numbers (e.g. 300 will make the text container 300 pixels wide.)

## *How do I remove the Sugarcane sidebar?*

This CSS example makes the sidebar invisible and moves the main text container to the center:

```css
  #sidebar { display: none; }
  #passages { margin-left: 0; }
```

## *How do I vertically center the text of all passages in Sugarcane?*

CSS:

```css
html, body { height:100%; margin-top: 0 !important; }
#passages { display:table; height:100%; }
.passage { display: table-cell; vertical-align:middle; }
```

Be advised this is a bit of a hack, and it may have unexpected behavior in some custom stylesheets.

## *How do I remove the vertical line to the left of Sugarcane passages (between the passages and the sidebar)?*

```css
#passages { border-left: 0px; padding-left: 0; }
```

## *How do I disable the browser's 'back' button in Sugarcane?*

In Twine 1.4: Under the menu **Story \> Special Passages \> StorySetting**, uncheck the box next to "Let the player undo moves."

## *How can I change the style of just one passage in Sugarcane?*

The simplest way may be to inject your CSS directly in the passage to have the special style:

HTML (inside the passage):

```html
<style>background {color: red;}</style>
```

Be advised using `<style>` tags outside of the page's `<head>` is technically invalid, but it's still supported by all browsers.

The other way is described directly below.

## *How do I change the styles for multiple, specific passages in Sugarcane?*

In Twine 1.4, you can add a new tag to a **stylesheet** passage and tag the desired story passages with that tag name. Only the passages with tagged with the class name will be affected by the stylesheet.
