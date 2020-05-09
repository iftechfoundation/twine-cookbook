# Snowman CSS

!!! Warning
    Overwriting existing CSS rules is an *advanced* technique.
    It has the potential to significantly change the presentation of content.

Snowman 1.X provides a limited set of CSS selectors and declarations.

## Snowman 1.X

```css
body {
  font: 18px "Helvetica Neue", Helvetica, Arial, sans-serif;
  color: #222;
}

#main {
  max-width: 38em;
  margin: 0 auto;
  line-height: 145%;
}

a {
  color: #222;
  text-decoration-color: #bbb;
}

a:hover {
  color: #cc8929;
  text-decoration-color: #cc8929;
}

a:active {
  color: #ffb040;
  text-decoration-color: #cc8929;
}
```

---

## Snowman 2.X

Snowman 2.X includes [normalize.css](https://github.com/necolas/normalize.css/) with its existing CSS code.

```css
body {
  font: 1.5em "Helvetica Neue", Helvetica, Arial, sans-serif;
  color: #222;
  margin: 0.5em;
}

tw-story {
  max-width: 35em;
  margin: 0 auto;
  line-height: 150%;
  display: block;
}

tw-passage {
  display: block;
}

a {
  color: #222;
  text-decoration-color: #ccc;
}

a:hover {
  color: #cc8929;
  text-decoration-color: #cc8929;
}

a:active {
  color: #ffb040;
  text-decoration-color: #cc8929;
}
```

---

## Snowman Links

Snowman uses the anchor element, `<a>`, for all links. However, as links are re-generated at the start of each passage, the pseudo-class `visited` will not have an effect. `hover`, however, will.

```css
a {
  color: blue;
}

a:hover {
  color: green;
}
```

---

## Overwriting CSS

### Snowman 1.X Passage

```css
#main { /* Your CSS Here */ }
```

### Snowman 2.X Passage

```css
tw-passage { /* Your CSS Here */ }
```
