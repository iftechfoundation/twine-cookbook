# Choosing a Story Format

A published HTML in Twine 2 does not contain the editor itself. That would be a waste of space! Instead, files are bundled with a [Story Format](../../terms/terms_storyformats.md).

## Explaining a Story Format

Think about a car. A *story format* is the *engine*. It drives the story, and works with the existing structure. Without it, the HTML file cannot "run!"

When a Twine 2 story is published, the story format is encoded and added to the HTML file. When run in a browser, the "engine" reads the story from the HTML and shows it to the user.

## Built-in Story Formats

There are multiple story formats that come with Twine 2, and they serve different purposes.

- **Harlowe** is the default story format, and is focused on making it easy to add basic interaction to your stories in a readable, concise way.

- **Snowman** is designed to be used by people who are familiar with writing JavaScript and CSS, two broadly-used Web technologies, and makes it easy to build a heavily-customized reading experience.

- **SugarCube** comes from the world of Twine 1. It gives readers the ability to save their progress into separate slots and provides a large collection of functionality for authors.

- **Chapbook** the first of a "second-generation" story formats, it is designed for newer users with advanced functionality built into its inserts and modifiers.

## Adding New Story Formats

Other developers and communities have created their own story formats.

New or versions of existing, loaded story formats can be added through the ["Add a New Format"](../../introduction/twine2_story_listing.md#add-a-new-format.md)

![Adding a Story Format](./images/starting-new-format.png "Adding a Story Format")

> **Note:** Story format URLs must end in `.js` and, for the online version, be on a public website or service using `http://` or `https://`. With the desktop version, the `file://` protocol can be used.

Once added, they can be selected from the Story Menu of a story and used during play, testing, and publishing.
