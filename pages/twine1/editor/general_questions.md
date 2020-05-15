# GENERAL QUESTIONS

## *How do I install some new CSS code / a new stylesheet?*

All CSS used in a Twine project must live in a passage with the tag **stylesheet**. Passages that have the right **stylesheet** tag have a purple frame.

1. Create a new **stylesheet** passage by right-clicking in your Twine workspace and choosing "New Passage Here" from the context menu. (You can also make an ordinary passage and manually enter **stylesheet** in the "tags" input.)

2. Copy the CSS code you want to add, and paste it into the **stylesheet** passage you just created.

That's it\! This CSS will now be available to your entire Twine project.

Note that **stylesheet** passages must contain *only* CSS code. Putting HTML or JavaScript in a **stylesheet** passage may cause unexpected results.

You can add as many **stylesheet** passages as you like, or you can keep all your CSS in one **stylesheet** passage--whichever is more convenient for you to use.

### *In CSS, what do the dots and number signs mean?*

A dot (.) indicates a class name. There can be many elements of the same class within an HTML page. For example, a class named "smurf" would look like this in the CSS:

```css
.smurf { color: blue; }
```

And like this in the HTML:

```html
<div class="smurf">Clumsy</div>
<div class="smurf">Brainy</div>
```

A number sign (\#) indicates an id. This means it's a unique name. There can be only one element with the given id in an HTML page. For example, an id named "highlander" would look like this in the CSS:

```css
#highlander { color: red; }
```

And like this in the HTML:

```html
<div id="highlander">Connor</div>
```

If the HTML also contained

```html
<div id="highlander">The Kurgan</div>
```

you would have a problem\!

(A `<div>` is just a general division in HTML. A nice thing about a `<div>` is that it doesn't have any effect on the contents of the tag except what's defined by the specified CSS class.)

## *How do I install some new JavaScript code?*

All JavaScript used in a Twine project must live in a passage with the tag **script**. Passages that have the right **script** tag have a brown frame.

1. Create a new **script** passage by right-clicking in your Twine workspace and choosing "New Script Here" from the context menu. (You can also make an ordinary passage and manually enter **script** in the "tags" input.)

2. Copy the JavaScript code you want to add, and paste it into the **script** passage you just created.

That's it\! This JavaScript will now be available to your entire Twine project.

Note that **script** passages must contain *only* JavaScript code. Putting HTML or CSS in a **script** passage may cause unexpected results.

You can add as many **script** passages as you like, or you can keep all your JavaScript in one **script** passage--whichever is more convenient for you to use.

## *How can I make my Twine playable offline? / How do I import jQuery?*

In Twine, go to the menu **Story \> Special Passages \> StorySetting**, scroll down to "Include the jQuery script library?" and check the box beside it.

OR

Add the text "requires jQuery" to any **script** passage.

Doing this will install a copy of jQuery 1.11 into the built HTML file, rather than using a Google CDN reference. This means the game will be playable even without an internet connection.

## *How do I import a new font from my local computer?*

In Twine, go to the menu **Story \> Import Font**. This will open a file browser window for you to choose the file of the font you'd like to add (for example, **myFunFont.ttf**). Select the desired font file and click "Open."

Now you can use the font family in the CSS of a **stylesheet** passage, like this:

```css
.passage {
  font-family: "myFunFont", sans-serif;
}
```

You can do one or the other, but you don't have to do both\!

> **Note:** No matter what the name of your passage is, you must refer to the imported font by the name it was imported as.
> **Note:** While all modern browsers support the font file formats TTF, OTF and WOFF, the font file format SVG is not supported by IE or Firefox, and the font file format E////OT is supported *only* by IE.

## *How do I import a Google web font?*

Browse the Google Webfont page for the font you want. For a single font, you can click the little middle "Quick
Use" button (a right arrow in a box). If you want multiple fonts, it's handy to add them to a collection and work with the CSS of that collection.

Once you've chosen your Google font, choose the @import tab to view the CSS code for the font. Copy this CSS code and paste it into a **stylesheet** passage. (See the top of this FAQ for how to make a **stylesheet** passage.)

Also, if you wish to use multiple fonts, you should, for convenience, add them all to a 'collection' while browing GFonts, and obtain the code specific to that collection.

Once the @import code is added to a **stylesheet** passage in your project, you may use it in CSS or HTML anywhere in the project.

> **Note**: In 1.4.1 or earlier, the `@import` code had to appear at the very start of the **stylesheet** passage that came first alphabetically. In 1.4.2 the `@import` code can appear anywhere (Twine manually hoists it where it needs to be.)

## *How do I use an image as the story page's background?*

This CSS example sets the background image to be **<http://www.funimages.com/images/happyLittleTree.png>**

```css
body { background-image: url("http://www.funimages.com/images/happyLittleTree.png"); }
```

If you've imported the image into your project, you can use the imported image syntax in your CSS:

```html
body { background-image: [img[happyLittleTree]]; }
```

CSS provides a lot of other background properties (such as [background-attachment](https://developer.mozilla.org/en-US/docs/Web/CSS/background-attachment), [background-position](https://developer.mozilla.org/en-US/docs/Web/CSS/background-position), [background-repeat](https://developer.mozilla.org/en-US/docs/Web/CSS/background-repeat)
and [background-size](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size)) that can be used as well.

## *How do I add hover text to some text in my passage?*

Here's sample HTML for your passage:

```html
  <abbr title="This hover text will appear on mouse over">This text is shown as usual.</abbr>
```

### *How do I disable the standard syntax so I can show ASCII art?*

You can use the monospace [syntax](syntax) like so:

```twee
    {{{ <<(@__@)>> }}}
```

## *How can the reader change a variable without navigating away from a passage?*

You may want to look into the [SugarCube story format](http://www.motoslave.net/sugarcube/docs/#macros-button)
extension. It provides **[click](http://www.motoslave.net/sugarcube/docs/#macros-click)** and **[button](http://www.motoslave.net/sugarcube/docs/#macros-button)** macros that can be used like so:

```twee
 <<click "Lose money">><<set $money -= 1>><</click>>
 <<button "Make money">><<set $money += 1>><</button>>
```
