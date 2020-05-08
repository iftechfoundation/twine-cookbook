# Reviewing JavaScript

[JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) is a programming language available in web browsers. It allows developers to write code that runs when a hypertext document is shown to a user.

## Document Object Model (DOM)

Web browsers provide any JavaScript code with a global object named **document**. This represents the entire HTML [document](https://developer.mozilla.org/en-US/docs/Web/API/Document) as an **object**. This allows code to read and change the document while it is shown to a user in a web browser.

## Story Formats Are JavaScript

Twine records the contents of a story as HTML. This is read and processed by a [story format](../terms/terms_storyformats.md) written in JavaScript.

## Story JavaScript

Every story has access to its [Story JavaScript](../introduction/twine2_passages_view.md#edit-story-javascript).

Any JavaScript code added to Story JavaScript will be run *before* any content of a story. It is a useful tool for adding more JavaScript code to a story or preparing values to be used before a story is run.
