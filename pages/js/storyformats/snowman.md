# Snowman JavaScript

Snowman does not come with any macros, but it does bundle the libraries of [Underscore](https://underscorejs.org/), [JQuery](https://jquery.com/), and [Marked](https://marked.js.org/#/README.md#README.md).

## Working with Templates

Because Snowman comes with Underscore, it supports writing JavaScript in passages using its template system.

### Arbitrary Code

The opening `<%` and closing `%>` template tags allow for writing arbitrary JavaScript in a passage.

```twee
<%
 let example = "Hi!";
 print(example);
%>
```

### Interpolating

The use of the opening `<%=` tag for templates *interpolates* any values it encounters. In other words, it is an easy way to include JavaScript values in passages.

```twee
I've made mistakes, Lord struck me down

<%= "Caught in a landslide, lost underground" %>

I hear them gates, swing open wide

<%= "Come close to midnight, hell fade me down" %>
```

### **print()**

Underscore provides the function **print()** inside of any template code. This can be used to "print" values from inside an arbitrary code template block.

```twee
Running from the violence

<%
  print("(Oh, oh. ");
  print("Oh, oh)");
%>

Running from the violence

```

## Global **s**

Inside any use of templates tags also have access to the global variable **s**. This is a short-hand for **window.story.state**, and it can be used to create the effect of story variables through creating global properties in JavaScript.

> **Note:** Any variables created in a code block or in a `<script>` element in Snowman are *local* to that scope. The only way to share values across passages is through global objects like **s**.

```twee
:: Untiled Passage
<%
  s.example = "Hi!";
%>

[[Another]]

:: Another
<%= s.example %>
```
