# CSS

[Cascading Style Sheets](https://en.wikipedia.org/wiki/Cascading_Style_Sheets) (CSS) is programming language for describing the presentation of HTML elements (*i.e.* the  colors, fonts, spacing, and general layout of a web page).  "Cascading" means rules move from a parent element to any children. Any specific rules also overrule any general ones.

CSS styles are associated with [HTML elements](https://en.wikipedia.org/wiki/HTML_element) using the element's (tag)name, id, classes, and/or other, possibly custom, [attributes](https://en.wikipedia.org/wiki/HTML_attribute).   Each built-in story format in Twine 2 uses different, sometimes custom, HTML elements to organize the story and then applies its own CSS rules.

## Story Stylesheet

When using Twine, additional CSS rules can be added through the Story Stylesheet screen. This CSS is inserted into the final story and provides an opportunity to override the color and formatting choices expressed in the story format's own stylesheet. (When using Twee, styles can be added using one or more passages tagged `stylesheet`.)

Considering the complex nature of CSS cascading, it is always highly recommended to use a story format's own macros where possible to change the presentation or layout of a story.

Common areas involved in story format styling include the full page or window, a sidebar (if present), and the current [passage](../terms/terms_passages.md) as a sub-area of the page.  Often, there is also a mechanism to style passages according to their tags (as assigned in Twine 2). See the CSS Selectors recipes for more details.
