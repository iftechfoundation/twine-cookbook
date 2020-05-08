# Reviewing CSS Selectors

Cascading StyleSheets (CSS) is a programming language for defining the presentation of HyperText Markup Language (HTML). Stylesheets "cascade" because values are passed from parent HTML elements to their children.

## Declarations

*Declarations* are written as a series of *properties* and *values*. Each has a property, colon (`:`), value, and end with a semicolon, `;`.

They "declare" the property has a certain value.

```css
color: red;
```

## Declaration Blocks

CSS is written in groups of declarations called *blocks*.

```css
{
  color: red;
  background: blue;
}
```

A *declaration block* begins with an opening curly bracket and ends with a closing curly bracket.

## Selectors

In order to apply the declarations to content, a *selector* is needed. This "selects" where in the document to apply the declarations.

There are many different possible selector combinations. Three of the most common are type, class, and ID.

### Type

A *type* selector finds one or more elements based on their name.

**CSS:**

```css
p {
  color: red;
}
```

**HTML:**

```html
<p>This would be red!</p>
```

### Class

A *class* selector finds one or more elements on their `class` attribute. Class selectors starts with a period, `.`.

**CSS:**

```css
.redFont {
  color: red;
}
```

**HTML:**

```html
<p class="redFont">This would be red!</p>
```

### ID

An *ID* selector finds one or more elements based on their `id` attribute. ID selectors start with a hash, `#`.

**CSS:**

```css
#redFont {
  color: red;
}
```

**HTML:**

```html
<p id="redFont">This would be red!</p>
```

## Ruleset

A *ruleset* is a combination of one or more selectors with a declaration block. They are often simply called "rules" or "CSS rules" when referring to them as groups.

**CSS:**

```css
body {
  font-size: 1.2em;
}
#redFont {
  color: red;
}
```

**HTML:**

```html
<body>
  <div id="redFont">This would be larger and in red!</div>
</body>
```
