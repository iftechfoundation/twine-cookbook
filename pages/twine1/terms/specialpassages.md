# Special Passages

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

There are certain passage names that have special meaning make stories look more polished. The most important is Start. It is the first passage displayed when a story is first loaded by a reader.

## StoryTitle, StorySubtitle, StoryAuthor

StoryTitle is where to set a story's title. StorySubtitle lets an author enter a brief subheading under the story, and StoryAuthor lets yan author write credit. Note that if an insert macro tags in these passages, they will be re-run every time the player changes passages.

## StoryMenu

The StoryMenu passage lets an author add items to the the menu that hovers in the upper-right corner of the page in the Jonah story format, or on the left side of the page in the Sugarcane story format. An author can link directly to passages in a story from this menu. An author might, for instance, put an "About the author" link in the menu that links to a passage containing a personal blurb.

Take care with the length of the menu items. A link will be displayed on a single line, even if it means that it will overlap a story's text.

Again, if an author puts macro tags in this passages, it will be re-run every time the player changes passages. This lets them make a "dynamic menu" that alters itself depending on the player's progress in the story.

## StorySettings

The StorySettings passage enables a number of special story options to be set.

- *Undo:* enables the player to "undo moves". In Sugarcane, this means being able to use the Back button in the browser. In Jonah, this means being able to use the "Rewind to here" link, and being able to click links in previous passages.

- *Bookmark:* enables the player to use the "Bookmark" link in Sugarcane and Jonah. On by default.

- *Hash updates:* this causes the current passage's bookmark URL to be automatically placed in the player's browser address bar whenever they change passages. This is off by default because the URLs can become very long and ugly quickly - opting against including the sidebar's "Bookmark" link, this may provide a useful alternative.

- *Prompt before closing:* If the player tries to reload or close the page, the browser will prompt for confirmation. This is useful for long games - it would be unfortunate if the player lost a lot of progress due to an idle key-press.

- *Don't use default CSS:* This removes most of the CSS used by the story format, allowing CSS programmers to write their own stylesheet redesigns more easily. Off by default - but including the text "blank stylesheet" in a stylesheet will set it on automatically.

- *ROT13:* obfuscates the story's HTML source to dissuade people from spoiling themselves by reading it. Off by default.

- *jQuery:* set this on if using custom scripts that rely on the jQuery library. Otherwise, leave off. Note: Twine 1.4 does not use the "$" variable, so jQuery can use it without $.noConflict().

- *Modernizr:* set this on if using custom scripts or stylesheets that rely on the Modernizr library. Otherwise, leave off.

## StoryIncludes

This passage is inspired by the "import" feature of various programming languages. It allows an author to merge the passages from other `.tws` or `.twee` files into a story's HTML file at build time. This lets an author work on a Twine project split into multiple files, each being edited independently of the other, but which are built into a single story. It also lets an author import a Twine file from a web URL without having to personally download it.

List the file paths and URLs that to include, line by line, in the StoryIncludes passage.

If an included file contains a passage with the same name as another included file's passage, an error will be raised when built.

## Annotations

There are times during Twine authors may wish to leave design notes for themselves or document certain aspects of a story map for future reference. **Annotation passages** should be used for this purpose. They are drawn large on the story map, allowing most of their contained text to be read without opening the editor.

Give a passage the tag "annotation" to make it an annotation passage.
