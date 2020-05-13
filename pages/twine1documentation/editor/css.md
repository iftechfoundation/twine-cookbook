# CSS

Cascading StyleSheets (CSS) is used to change the color, typeface, or other parts of the story's visual appearance.

When a story is first loaded, all passages tagged `stylesheet` are added to the page's CSS.

> **Note:** Tags are case-sensitive, so tagging a passage `Stylesheet` or `STYLESHEET` will have no effect. There is also no guaranteed order in which rules are added, so conflicting rules may produce unpredictable results.

## CSS Summary

CSS is written with *declarations* and *selectors*.

A *declaration* "declares" something, associates a property with a value, and a *selector* "selects" through defining what the declarations affects in HTML.

```css
SELECTORS {
  property-name : value ;
  property-name : value ;
}
```

There are three primary forms of selectors in CSS:

- **type:** these select different elements like `<p>` or `<div>`. They are written using the form of `p {}` or `div {}`.
- **class:** these select elements based on their `class` attribute. They are written using the form `.className`.
- **id**: these select elements based on their `id` attribute. They are written using the form `#idName`.

## Example Selectors

| Selector                                    | Description                                                                                                                                                                                                                        |
| ------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `.passage`                                  | All the passages on the page. In Sugarcane, unlike Jonah, there's only ever one such passage. Note that this element fades in whenever you change passages, whereas `#passages` remains constant. |
| `.passage:last-child`                       | In Jonah, this solely targets the "current" passage - the one at the bottom of the page.                                                                                                                                  |
| `.passage:not(:last-child)`                 | In Jonah, this solely targets the past passages.                                                                                                                                                                                   |
| `.passage .title`                           | The passage title in Jonah.                                                                                                                                                                                                        |
| `.passage .toolbar`                         | The passage toolbar in Jonah.                                                                                                                                                                                                      |
| `.passage a`                                | Every link in a passage.                                                                                                                                                                                                   |
| `.passage a:hover`                          | A link that the cursor is hovering over.                                                                                                                                                                                           |
| `.passage a:active`                         | A link that is in the midst of being clicked. (You can use this to make a link "light up" when clicked.)                                                                                                                           |
| `.passage a.internalLink`                   | Only links to other passages (and not, say, other websites).                                                                                                                                                                       |
| `.passage a.visitedLink`                    | Every link to another passage that the player's visited at least once.                                                                                                                                                             |
| `.passage a.internalLink:not(.visitedLink)` | Every link to another passage that the player's not visited yet.                                                                                                                                                                   |
| `.passage a.externalLink`                   | Only external links. Doesn't include HTML `<a>` links.                                                                                                                                                                             |
| `.passage li`                               | Bulleted or numbered list items in a passage.                                                                                                                                                                                      |
| `.passage img`                              | Images in a passage.                                                                                                                                                                                                      |
| `.passage hr`                               | Horizontal lines in a passage.                                                                                                                                                                                                     |
| `.disabled`                                 | Links that are not longer available to the reader, created through the `<<choice>>` macro, or by turning the Undo StorySetting to off.                                                                       |
| `#passages`                                 | A container for all passages displayed on the page.                                                                                                                                                                                |
| `body`                                      | The body of the HTML page -- a great place to change the typeface for the entire page. But, individual elements' styles will usually override this.                                                                                |
| `#sidebar`                                  | The Sugarcane sidebar, containing the StoryMenu.                                                                                                                                                                                   |
| `#sidebar li`                               | List items inside the Sugarcane sidebar.                                                                                                                                                                                           |
| `#floater`                                  | The Jonah StoryMenu (which usually only contains 'Restart Story')                                                                                                                                                                  |
| `#footer`                                   | The footer at the bottom of Jonah (e.g. "This story was built with Twine and is powered by TiddlyWiki").                                                                                                                           |
| `#credits`                                  | The credits in Sugarcane's sidebar (e.g. "This story was built with Twine and is powered by TiddlyWiki").                                                                                                                          |

## Example CSS code

This hides all passage titles, *except for the current passage*, from view in the Jonah story format:

```css
.passage:not(:last-child) .title { display: none }
```

### Tagged Stylesheets

Normally, every stylesheet applies to all of the passages. If a passage has additional tags apart from `stylesheet` (for instance, `stylesheet forest`), then it will only apply to passages which themselves have that tag. This allows for easily making different sections of a story have different styles to distinguish them.

### A note about Jonah

Tagged CSS in Jonah that uses the `.passage` selector will continue to affect the tagged passage even when the player advances to a different-tagged passage. But, CSS that targets the whole page, such as the `body` element, will not be retained. So, for instance, different link colours for a passage will remain on the passage as the game progresses, but changes to the page background will not.

### Transition stylesheets

A special tag exists: `transition`. If a stylesheet has this tag, then its styling will replace the default passage transition animation.

| Selector          | Description                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `.transition-out` | A passage that is disappearing. This is only used in Sugarcane and similar formats. The styles in this CSS block define the *final* state of the passage's appearance - for instance, if this passage is fading out, its `.transition-out` style could have `opacity: 0;`.                                                                                                                                                   |
| `.transition-in`  | A passage that is appearing. The styles in this CSS block define the *initial* state of the passage's appearance - for instance, if this passage is fading in, its `.transition-in` style could have `opacity: 0;`.                                                                                                                                                                                                          |
| `.passage`        | Passages should have additional CSS attributes: `transition` (used by most browsers) and `-webkit-transition` (used by certain older mobile browsers). This defines how long and in what manner the `.transition-in` styles are removed when passages appear, and how the `.transition-out` styles are added when passages disappear. See [this documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/transition). |

As an example, the following CSS defines a smooth "dissolve" transition:

```css
.transition-in {
  opacity: 0;
  position: absolute;
}
.passage {
  transition: 1s;
  -webkit-transition: 1s;
}
.transition-out {
  opacity: 0 !important;
  position: absolute;
}
```
