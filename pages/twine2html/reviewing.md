# Reviewing HTML

HyperText Markup Language (HTML) describes the structure of document. The language has a series of *elements* that "markup" content to define how it is presented and arranged.

## Elements

HTML documents start with a `<html>` element. It has an *opening tag* and *closing tag*.

```html
<html></html>
```

An *opening tag* begins with a less-than sign, `<`, the name of the element, and greater-than sign, `>`. Following the opening tag is any content that is part of the element. It ends with a closing tag, a less-than sign, `<`, a backslash, `/`, the name of the element, and a greater-than sign, `>`.

- **Opening Tag:** `<html>`
- **Content:**
- **Closing Tag** `</html>`

Elements exist in connection to each other in a parent and child relationship.

```html
<html>
  <body></body>
</html>
```

If one or more elements are content inside an element, it is their *parent*.

- **Parent:** `<html>`
- **Children:** `<body>`

## Head and Body

HTML documents start with `<html>`. This element has two children: `<head>` and `<body>`.

### `<head>`

The `<head>` element contains information about the document such as its title, author, and other details about the document.

```html
<html>
  <head>
    <title>Example Document!</title>
  </head>
</html>
```

### `<body>`

The `<body>` element contains the content of a document. Anything that is part of the document and not a child of the `<head>` will be in the `<body>` element.

```html
<html>
  <body></body>
</html>
```

## Common HTML Elements

The most current version of HTML allows for new elements to be added and used in a document without issue. However, there are many common HTML elements defined in earlier versions and frequently used to structure documents.

- **`<p>`:** Paragraph element, `<p>`, is most commonly used to store large groups of text.
- **`<strong>`:** Strong emphasis, `<strong>`, gives a **strong emphasis** to its content.
- **`<em>`:** Emphasis, `<em>`, gives an *emphasis* to its content.
- **`<div>`:** Division, `<div>`, "divides" up a document. It is very common to use `<div>` elements to logically separate content in a larger document.
- **`<a>`**: Anchor element. Hyperlinks are created through using *anchors*, `<a>`.

## Attributes

All elements have access to *attributes*. Inside of the opening tag of an element, values can be used to configure or adjust how the element is displayed or understood.

Attributes are written in a `property="value"` format where the *property* is assigned a "value" inside of quotation marks.

```html
<a href="https://www.google.com/">Link to Google</a>
```

The most common attribute is *href* (hyper-reference) as used with `<a>`. It defines what the hyperlink links to from the anchor. However, there is a large number of possible [attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes).

### `id`

All elements can use the `id` attribute. It should be a unique value within the document. It's an *identification*.

```html
<div id="example">
Content
</div>
```

When working with CSS, using the `id` attribute also allows its unique value to be "selected" and styled in certain ways.

### `class`

All elements can use the `class` attribute. It can be a repeating value within the document. It's a *classification* that can be used across multiple elements.

```html
<div class="example">
Content
</div>
```

When working with CSS, using the `class` attribute also allows its value to be used multiple times.

## Using HTML in Twine

HTML elements like `<p>` can be used inside of passages in Twine. In fact, all story formats support using elements to better structure content.
