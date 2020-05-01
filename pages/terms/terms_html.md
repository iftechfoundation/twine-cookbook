# HTML

The HyperText Markup Language ([HTML](https://en.wikipedia.org/wiki/HTML)) is the standard for all documents designed for a web browser. It consists of a series of [elements](https://developer.mozilla.org/en-US/docs/Glossary/Element) defining its structure and the layout of its content.

## Story Format Layout

Each [story format](terms_storyformats.md) handles its own layout and HTML structure. While [CSS](terms_css.md) can be used to style its elements, it is often recommended to use any exisitng macros for this purpose in a story format, if available.

* [Harlowe: Named Hooks](https://twine2.neocities.org/#markup_named-hook)
* [SugarCube: CSS Selectors](https://www.motoslave.net/sugarcube/2/docs/#css-example-selectors)
* [Snowman: HTML Elements](https://videlais.github.io/snowman/2/htmlandcss/elements.html)
* [Chapbook: Customization](https://klembot.github.io/chapbook/guide/customization/)

## Twine 2 HTML

All data of a Twine 2 story is stored as a series of HTML elements within a page according to the [HTML Output Specification](https://github.com/iftechfoundation/twine-specs/blob/master/twine-2-htmloutput-spec.md).

**Example:**

```html
<tw-storydata>
  <style
    role="stylesheet"
    id="twine-user-stylesheet"
    type="text/twine-css">
  </style>
  <script
    role="script"
    id="twine-user-script"
    type="text/twine-javascript">
  </script>
  <tw-tag
    name="tagName"
    color="orange">
  </tw-tag>
  <tw-passagedata
        pid="1"
        name="Start"
        tags="tag1 tag2"
        position="102,99"
        size="100,100">
    Some content
    </tw-passagedata>
</tw-storydata>
```
