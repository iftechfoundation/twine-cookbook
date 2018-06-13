# What is Twee?

Twee is the source code of a Twine [Story](../terms/terms_stories.md). In Twine 1, Stories could be exported into its source, changed, and imported again. Twine 2 has moved away from this functionality, but has been heavily influenced through having sections (passages in Twine 1) where the user can add [CSS](../terms/terms_css.md) (Story Stylesheet) and [JavaScript](../terms/terms_javascript.md) (Story JavaScript).

## Notation

Twee does not have an official specification. However, the notation is commonly written as a series of three parts for the header of each passage: sigil, passage name, and optional tag section. The content of the passage continues after the header with a single empty line between passage headers.

**Example Twee Notation:**
```
:: Snoopy [dog peanuts]
Snoopy is a dog in the comic Peanuts.

:: Charlie Brown [person peanuts]
Charlie Brown is a person in the comic Peanuts

```
The sigil consists of two colons (":") followed by a space and the name of the passage. If any tags are present, they are included in brackets with a single space between them.

## Differences between Twee and Twine 2 Terminology

Twee follows the convention of using the User Stylesheet and User Script named passages that started with Twine 1.

Twine 2 stories converted into Twee retain these names and the corresponding tags of "stylesheet" and "script" depending on the type of content.

**Example Stylesheet:**
```
:: UserStylesheet[stylesheet]
```

**Example JavaScript:**
```
:: UserScript[script]
```
