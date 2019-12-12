# What is Twee?

Twee is the source code of a Twine [story](../terms/terms_stories.md). In Twine 1, stories could be exported into its source, changed, and imported again. Twine 2 has moved away from this functionality, but has been heavily influenced through having sections (passages in Twine 1) where the user can add [CSS](../terms/terms_css.md) (Story Stylesheet) and [JavaScript](../terms/terms_javascript.md) (Story JavaScript).

## Notation

Starting with Twee 3, there is [a standard for reading and writing Twee](https://github.com/iftechfoundation/twine-specs/blob/master/twee-3-specification.md) when working with Twine 2 passages.

Twee 3 notation is written as a series of four parts for the header of each passage:

* Sigil: (Required) Two colons (":") followed by a space
* Passage Name: (Required) The name of the passage
* Tags: (Optional) Optional tags
* Metadata: (Optional) Information about the passage

The content of a passage continues until the next header of a passage is found or the input ends with at least a single empty line between passage headers.

**Example Twee Notation:**
```
:: Snoopy [dog peanuts]
Snoopy is a dog in the comic Peanuts.

:: Charlie Brown [person peanuts] {"position":"600,400","size":"100,200"}
Charlie Brown is a person in the comic Peanuts

```

## Special Passage Names

Some compilers understand and process certain keywords differently. The following is a common set of case-sensitive reserved passage names across Twine 1 and Twee 3.

#### Start (Twine 1 and Twee 3)

The first passage.

```
:: Start
A beginning!
```

#### StoryTitle (Twine 1 and Twee 3)

The title of the story.

```
:: StoryTitle
A Named Story
```

#### StorySubtitle (Twine 1)

The subtitle of the story.

```
:: StorySubtitle
The subtitle of this story
```

#### StoryAuthor (Twine 1)

The author of the story.

```
:: StoryAuthor
John Smith
```

#### StoryMenu (Twine 1)

Corresponds to the menu that hovers in the upper-right corner of the page in the Jonah story format, or on the left side of the page in the Sugarcane story format.

```
:: StoryMenu
Content of the story menu!
```

#### StorySettings (Twine 1)

Used to specify certain options and settings.

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
#### StoryIncludes (Twine 1)

Includes, "imports", other local or remote files during the HTML compilation process. In Twine 1.4.2, both Twine Story (.tws) and Twine Source (.twee) files can be used.

```
:: StoryIncludes
localfile.tws
```

#### StoryData (Twee 3)

A JSON chunk encapsulating various Twine 2-compatible details about the story.

* ifid: (Required) IFID of the story
* format: (Optional) Story format
* format-version: (Optional) Story format version
* start: (Optional) PID of starting passage
* tag-colors: (Optional) Pairs of tags and colors
* zoom: (Optional) Decimal zoom level

```
:: StoryData
{
	"ifid": "D674C58C-DEFA-4F70-B7A2-27742230C0FC",
	"format": "SugarCube",
	"format-version": "2.28.2",
	"start": "My Starting Passage",
	"tag-colors": {
		"bar": "green",
		"foo": "red",
		"qaz": "blue"
	},
	"zoom": 0.25
}
```

## Special Tag Names

Twee 3 defines two special case-sensitive lowercase passage tags: `stylesheet` and `script`.

(Passages are also loaded according to alphabetical order if others exist with the same special passage tags.)

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
