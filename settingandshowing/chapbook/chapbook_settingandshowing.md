# "Setting and Showing Variables": Chapbook (v1.0.0)

## Summary

In Chapbook **all** variables are initialised and/or updated within the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) of a passage, this section is always added at the beginning of the passage and there can only be one such section per passage.

The _Vars Section_ is separated from the passage's normal text by two dashes (```--```), and you can [display the contents](https://klembot.github.io/chapbook/guide/state/displaying-variables.html) of a variable using ```{insert}``` markup.

<div class="alertbox information"><strong>Note:</strong> Because you can [embed the contents of one passage within another](https://klembot.github.io/chapbook/guide/modifiers-and-inserts/embedding-passages.html) using the ```{embed passage:}``` insert, it is possible to update a variable using _Vars Section_ a child passage.</div>

## Live Example

<section>
<iframe src="chapbook_settingandshowing_example.html" height=400 width=90%></iframe>


Download: <a href="chapbook_settingandshowing_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Setting and Showing Variables in Chapbook

:: Start
numberVariable: 5
wordVariable: "five"
phraseVariable: "The value"
--

{phraseVariable} is {numberVariable} and {wordVariable}.

{embed passage: "Increment number"}

The number variable was incremented by one to {numberVariable}.

:: Increment number
numberVariable: numberVariable + 1
--

```

Download: <a href="chapbook_settingandshowing_twee.txt" target="_blank">Twee Code</a>

