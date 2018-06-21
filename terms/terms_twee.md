# What is Twee?

Twee is the source code of a Twine [story](../terms/terms_stories.md). In Twine 1, stories could be exported into its source, changed, and imported again. Twine 2 has moved away from this functionality, but has been heavily influenced through having sections (passages in Twine 1) where the user can add [CSS](../terms/terms_css.md) (Story Stylesheet) and [JavaScript](../terms/terms_javascript.md) (Story JavaScript).

## Notation

Twee does not currently have an official specification. However, the notation is written as a series of three parts for the header of each passage:

* Sigil: Two colons (":") followed by a space
* Passage Name: The name of the passage
* Tags: Optional tags

The content of a passage continues until the next header of a passage is found or the input ends with at least a single empty line between passage headers.

**Example Twee Notation:**
```
:: Snoopy [dog peanuts]
Snoopy is a dog in the comic Peanuts.

:: Charlie Brown [person peanuts]
Charlie Brown is a person in the comic Peanuts

```

## Special Passage Names

Because Twee does not currently have a specification, some compilers understand and process certain keywords differently. The following is a common set of case-sensitive reserved passage names.

#### Start

The first passage.

```
:: Start
A beginning!
```

#### StoryTitle

The title of the story.

```
:: StoryTitle
A Named Story
```

#### StorySubtitle

The subtitle of the story.

```
:: StorySubtitle
The subtitle of this story
```

#### StoryAuthor

The author of the story.

```
:: StoryAuthor
John Smith
```

#### StoryMenu

In Twine 1.4.2, the StoryMenu passage coresponds to the menu that hovers in the upper-right corner of the page in the Jonah story format, or on the left side of the page in the Sugarcane story format.

```
:: StoryMenu
Content of the story menu!
```

#### StorySettings

Used to specify certain options and settings.

*Twine 1.4.2 Settings:*

* Undo: enables the player to "undo moves." In Sugarcane, this means being able to use the Back button in the browser. In Jonah, this means being able to use the “Rewind to here” link, and being able to click links in previous passages.

* Bookmark: enables the player to use the “Bookmark” link in Sugarcane and Jonah. On by default.

* Hash updates: this causes the current passage's bookmark URL to be automatically placed in the player's browser address bar whenever they change passages. This is off by default because the URLs can become very long and ugly quickly.

* Prompt before closing: If the player tries to reload or close the page, the browser will prompt for confirmation. This is useful for long games - it would be unfortunate if the player lost a lot of progress due to an idle key-press.

* Don't use default CSS: This removes most of the CSS used by the story format, allowing CSS programmers to write their own stylesheet redesigns more easily. Off by default - but including the text “blank stylesheet” in a stylesheet will set it on automatically.

* ROT13: obfuscates the story's HTML source to dissuade people from spoiling themselves by reading it. Off by default.

* jQuery: include the library or not

* Modernizr: include the the library or not

```
:: StorySettings
undo:on
bookmark:on
hash:on
exitprompt:on
blankcss:on
obfuscate:rot13
jquery:on
modernizr:on
```
#### StoryIncludes

Includes, "imports", other local or remote files during the HTML compilation process. In Twine 1.4.2, both Twine Story (.tws) and Twine Source (.twee) files can be used.

```
:: StoryIncludes
localfile.tws
```

#### UserStylesheet

Although not an official keyword in most compilers, stories converted into Twee, or those without an existing passage tagged with "stylesheet", will sometimes be given a passage with the name "UserStylesheet". In most cases, this will also have the tag "stylesheet".

In Twine 2, this passage is the equivalent of Story Stylesheet.

```
:: UserStylesheet[stylesheet]
```

#### UserScript

Although not an official keyword in most compilers, stories converted into Twee, or those without an existing passage tagged with "script", will sometimes be given a passage with the name "UserScript". In most cases, this will also have the tag "script".

In Twine 2, this passage is the equivalent of Story JavaScript.

```
:: UserStylesheet[stylesheet]
```

## Special Tag Names

Most Twee compilers understand two case-sensitive, lowercase tag names: stylesheet and script. 

Passages are also loaded according to alphabetical order if others exist with the same special keywords in their own tags.

#### Stylesheet

Any additional or overriding CSS rules for the story.

```
:: UserStylesheet[stylesheet]
```

#### Script:

Any additional or overriding JavaScript code for the story.

```
:: UserScript[script]
```
