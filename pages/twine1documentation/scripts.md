# Scripts

Just as a passage with the tag `stylesheet` will have its contents treated as CSS style rules, the `script` tag to include custom Javascript in your story. All passage with this tag are executed when the game first loads, which can do two things:

- Define custom macros made in Javascript by other Twine users.
- Modify how the Twine engine will work. To do this properly requires careful inspection of the Twine engine.

The execution order of passages tagged `script` is based on the alphabetical order of the script passages' names.

> **Note:** `script` passages must *only* contain Javascript.

## Requesting jQuery

[jQuery](http://jquery.com) can be used in scripts to manipulate the page's structure, use AJAX, or just make general coding easier. jQuery can be requested through simply using the case-insensitive words "requires jQuery" in a comment or a string inside the code:

```twee
  //requires jquery
```

> **Note:** [Modernizr](http://modernizr.com) can be used with "requires Modernizr".

## `prerender` and `postrender`

Two objects exist in the Twine engine that are designed for custom script writers: `prerender` and `postrender`. These JavaScript function properties will be run every time a passage is rendered.

A `postrender` function looks something like this:

```javascript
postrender.hello = function(a) {
  ...
  a.className += "hello"; // An example of 'a'
  console.log(this.title); // An example of 'this'
  ...
};
```

When **postrender.hello()** is called, *this* is the Passage object which is currently being rendered, and the first argument, `a`, is the `<div class="body content">` element into which the passage's code has been rendered.

`postrender` functions are called just after the passage's code is rendered into the `<div>`. `prerender` functions are called just before then.

### Passage Objects

Passage objects have the following structure (plus some other less useful properties):

- **title**: the string name of the passage.
- **tags**: an array of strings representing the passage's tags.
- **text**: the raw code of the passage.
- **processText()**: the code of the passage with some substitutions made the "nobr" tag, if present, removes line breaks, and imported image syntax has the image's base64 data inserted.
