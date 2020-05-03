# How to Choose a Story Format

When you publish your story to a file, that file doesn't contain the entire Twine editor. That'd be wasteful, since most people reading your story won't be interested in editing it. Instead, your story is bound to a story format, whose job is to show your story in a playable format.

This process is a little like taking a word processing document, which is easy to make changes to, and running it through a printing press and then binding the results as a book – which, apart from scribbling in the margins, you aren't able to change. At the same time, a book is a lot more enjoyable to read than a word processing document.

Built-in Story Formats
There are three story formats that come with Twine 2.0, and they serve different purposes.

Harlowe is the default story format, and is focused on making it easy to add basic interaction to your stories in a readable, concise way. Its home page is here.

Snowman is designed to be used by people who are familiar with writing JavaScript and CSS, two broadly-used Web technologies, and makes it easy to build a heavily-customized reading experience. Its home page is here.

SugarCube comes from the world of Twine 1, so if you are already familiar with the story formats that were used by Twine 1, you'll find it comfortable to use. You can also draw on the vast number of Twine 1-related resources on the web and use them as-is. SugarCube also has the ability for your reader to save their progress into separate slots, similar to a console video game. Its home page is here.

Adding New Story Formats
There may also be other story formats on the Internet; anyone can create one if they're interested. If you've found one that you'd like to use for your Twine project, you can add it to the story list.

How Do I Decide Which One To Use?
Each format has a different look and feel out-of-the-box, but all of them allow you to customize their apperance. And all of them are designed to work reasonably well on a mobile browser, too. Instead, the best way to judge is to take a look at the project pages and decide which will be the easiest to accomplish what your project needs.

It can also be helpful to see how scripting in each format looks. Here's how you would write the script for a door that can only be opened if the reader previously found a key of a particular color:

Harlowe:

(if: $hasKey)[It looks like the $keyColor key will [[open the door]].]
(else:)[No way forward here, unfortunately.]
Snowman:

<% if (s.hasKey) { %>
It looks like the <%= s.keyColor %> key will [[open the door]].
<% } else { %>
No way forward here, unfortunately.
<% } %> 
SugarCube:

<<if $hasKey>>
It looks like the $keyColor key will [[open the door]].
<<else>>
No way forward here, unfortunately.
<</if>>