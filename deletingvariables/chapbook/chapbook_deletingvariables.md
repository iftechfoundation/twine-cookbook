# "Deleting Variables": Chapbook (v1.0.0)

## Summary

While variables created using the `[JavaScript]` modifier can be deleted within their blocks, any created within the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) can simply be set to [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) to make them unable to be shown within an expression using the *[engine.state.set()](https://klembot.github.io/chapbook/guide/advanced/using-javascript-in-passages.html)* function.

## Live Example

<section>
<iframe src="chapbook_deletingvariables_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_deletingvariables_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Chapbook: Deleting Variables

:: Start
color: "red"
--
[JavaScript]
engine.state.set("color", undefined)
[continued]
What is color? {color}

```

Download: <a href="chapbook_deletingvariables_twee.txt" target="_blank">Twee Code</a>
