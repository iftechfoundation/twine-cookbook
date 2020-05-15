# SugarCube CSS

!!! Warning
    Overwriting existing CSS rules is an *advanced* technique. It has the potential to significantly change the presentation of content.

All SugarCube stories follow the same [HTML structure](../../html/storyformats/sugarcube.md#sugarcube-html).

The SugarCube documentation has extensive details on the [selectors available](https://www.motoslave.net/sugarcube/2/docs/#css-example-selectors) in the story format.

---

## Overwriting SugarCube CSS

### SugarCube Passage

```css
.passage { /* Your CSS Here */ }
```

### SugarCube Links

SugarCube uses the anchor element, `<a>`, to create hyperlinks.

```css
.passage a {  /* Your CSS Here */ }
.passage a:hover {  /* Your CSS Here */ }
.passage a:active {  /* Your CSS Here */ }
```

### Passage Names

All passages are given the *id* attribute value as their name with the prefix of `passage-`.

Any with spaces between words or characters are converted into hyphens. All letters are converted into lowercase.

**Example:**

```css
#passage-untitled-passage { /* Your CSS Here */ }
```

If a passage is included via the `<<include>>` macro, its name is added to the class list for the passage element. It can be used as a class selector instead.

**Example:**

```css
.passage-additional-passage { /* Your CSS Here */ }
```
