# CSS

[Cascading Style Sheets](https://en.wikipedia.org/wiki/Cascading_Style_Sheets) (CSS) is a style sheet language for describing the presentation of elements in HTML. 

## Story Stylesheet

Each built-in story format in Twine 2 defines or understands its core HTML elements differently. While a story format may provide new elements, it is always highly recommended to use its own macros, if provided, to change the presentation or layout.

### Harlowe

Harlowe uses the `tw-story` element as a container for the currently shown passage, `tw-passage`. The sidebar is inside (a child of) each passage and is the element `tw-sidebar`.

The story data is storied in the `tw-storydata` element and it contains the story metadata as atttributes of the following:
* creator: the tool used to create the Story, usually "Twine"
* creator-version: version of the tool
* format: the story format
* format-version: the version of the story format
* [IFID](../terms/terms_stories.md): the Interactive Fiction IDentifier created with the Story

### SugarCube

SugarCube uses the [*id* CSS selector](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors) for its elements. Like Harlowe, the "story" *id* is applied to the container of the element containing the "passages". Unlike Harlowe, the currently shown passage's *id* is named after a combination of "passage-" and then the name of the passage with hyphens ("-") used to fill in any spaces. The currently shown passage is also given the [*class* CSS selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors) "passage".

The *id* of the sidebar is "ui-bar".

### Snowman

Snowman follows a combination of both Harlowe and SugarCube patterns. It has a `tw-storydata` element with the same attributes generated for the story. It also contains an element with the *id* CSS selector of "passage" for the currently shown passage. 
