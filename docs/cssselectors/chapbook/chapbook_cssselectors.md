# "CSS Selectors": Chapbook (v1.0)

## Summary

This example shows how to use [CSS](../../terms/terms_css.md) selectors to style different areas of the page. In Chapbook, the *backdrop* covers the whole page, the *page* is like a "story" area in other story formats, and the first `<div>` inside the `<article>` is the main passage area.

```html
<div id="backdrop">
  <div class="page">
    <header>
      <div class="left"></div>
      <div class="center"></div>
      <div class="right"></div>
    </header>
    <article>
      <div></div>
    </article>
    <footer>
      <div class="left"></div>
      <div class="center"></div>
      <div class="right"></div>
    </footer>
  </div>
</div>
```

## Live Example

<section>
<iframe src="chapbook_cssselectors_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_cssselectors_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```twee
:: StoryTitle
CSS Selectors in Chapbook

:: UserStylesheet[stylesheet]
#backdrop {
    border: 5px solid green;
}

#page {
    border: 2px solid red;
}

#page article>:first-child {
    border: 1px solid blue;
}

:: Start
The backdrop has a green border; it contains this page (red border) and the article (blue border).

[[Second]]

:: Second
This passage also has a blue border.

```

Download: <a href="chapbook_cssselectors_twee.txt" target="_blank">Twee Code</a>
