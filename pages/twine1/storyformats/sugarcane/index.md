# Sugarcane

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

## Visual Description

This displays the story with white text on a black background. Players can only see one passage at a time, though they ca use their browsers' back buttons to return to a previous passage.

Sugarcane has a sidebar menu that may contain these entries:

- *Bookmark:* This serves as a link directly to the current passage, and is automatically updated throughout the game. Players can save their game by copying the URL from this link. (If the StorySettings disallows the ability to undo, then this is unavailable to players, as bookmarking can obviously be used to undo moves.

- *Rewind:* If a Sugarcane passage has the tag "bookmark", then each visit to this passage will create an entry in the Rewind menu as a 'checkpoint'. By using that menu, they can rewind the game to that particular state. For obvious reasons, this is not particularly useful if the StorySettings allows the Bookmark menu to also be present.

## CSS

### Base CSS

```css
/* Sidebar */
#sidebar {
    position: fixed;
    list-style: none;
    width: 12em;
}
#sidebar #title, #sidebar #credits  {
    cursor: auto;
}
#sidebar #storySubtitle, #sidebar #storyMenu {
    display: block;
}
.menu {
    position: absolute;
    display: none;
    z-index: 5;
}
/* Passages container */
#passages {
    margin-left: 18.2em;
    position:relative;
}
/* Links */
.passage a {
    color: #4d6ad8;
}
a.internalLink, a.externalLink, a.back, a.return, [data-passage], .menu div {
    cursor: pointer;
}
a.brokenLink {
    background-color: red;
    color: #000;
}
.marked {
    background-color: #f66;
    color: #000;
}
.marked[title] {
    cursor: help;
}
.passage li[data-bullet] {
    list-style-type: none;
}
.passage li[data-bullet]:before {
    content: attr(data-bullet);
    position: relative;
    left: -1em;
}
#storeArea {
    display: none;
}
#noscript {
    margin-left: 18.2em;
    font-size: 1.2em;
    font-weight: bold;
}
/* HTML4 compatibility */
img {
    vertical-align:bottom;
}
@media screen and (max-width: 640px) {
    #sidebar {
        position: static;
        margin: 0 auto;
        padding: 0;
    }
    body #sidebar li  {
        text-align: center;
    }
    #passages {
        min-height: 100vh;
        margin-left: 0em;
    }
}
#loadingbar {
    position:fixed;
    top:0;
    left:0;
    border-top: solid #4d6ad8 6px;
    transition: width 0.5s;
}
```

### Default CSS

This CSS completes the default Sugarcane look-and-feel. This code is removed if "Don't use the Story Format's default CSS" is selected in StorySettings or if the words "blank stylesheet" appear anywhere within a comment in the story's stylesheets.

```css
body {
    background-color: #000;
    color: #fff;
    font-family: Verdana,sans-serif;
    font-size: 62.5%;
    margin: 4em 15% 5% 5em;
}
#sidebar {
    left: 7.5em;
    margin: 0;
    padding: 0 1em 0 0;
    font: bold 1.1em Verdana,sans-serif;
}
#sidebar ul {
    padding: 0;
}
#sidebar li {
    color: #333;
    text-align: right;
    background-repeat: no-repeat;
    margin-bottom: 1em;
    line-height: 1.4em;
    list-style: none;
}
#sidebar li a {
    color: #333;
    text-decoration: none;
}
#sidebar li a:hover, #sidebar #title a:hover, #snapback:hover, #restart:hover {
    color: #fff;
    cursor: pointer;
    text-decoration: none;
}
#sidebar #title {
    font-size: 150%;
}
#sidebar #title, #sidebar #title:hover, #sidebar #title a {
    color: #999;
}
#sidebar #storySubtitle {
    font-size: 75%;
}
#storyAuthor {
    font-size: 50%;
}
#sidebar #storyMenu {
    line-height: 2.5em;
    margin-bottom: .5em;
    color: #999;
    cursor: auto;
}
#sidebar #credits {
    padding-top: 2em;
    font-weight: normal;
    font-size: 80%;
}
#sidebar #credits:hover {
    color: #333;
}
#sidebar #credits a {
    text-decoration: none;
}
#passages {
    border-left: 1px solid #333;
    padding-left: 1.5em;
}
.menu {
    background-color: #343434;
    color: #fff;
    opacity: .9;
    border: 1px solid #fff;
    text-align: left;
    font: 1.1em Verdana;
    line-height: 2em;
}
.menu div {
    padding: 0 .4em;
}
.menu div:hover {
    cursor: pointer;
    background-color: #fff;
    color: #343434;
}
.passage {
    font-size: 1.2em;
    line-height: 175%;
    margin-bottom: 2em;
    text-align: left;
}
.passage a {
    font-weight: bold;
    text-decoration: none;
}
.passage a:hover {
    color: #8ea6ff;
    text-decoration: underline;
}
.content > ul {
    padding-top: 1.3em;
}
.passage ul, .passage ol {
    margin-left: .5em;
    padding-left: 1.5em;
}
.passage li {
    margin-right: 6em;
}
.passage table {
    border-collapse: collapse;
    font-size: 100%;
    margin: .8em 1.0em;
}
.passage th,.passage td,.passage tr,.passage caption {
    padding: 3px;
}
.passage hr {
    height: 1px;
}
.passage center {
    max-width:50%;
    margin:auto;
}
.marked {
    margin-right: 12px;
    padding: 3px;
}
.disabled {
    font-weight: bold;
    color: #333;
}
@media screen and (max-width: 640px) {
    body {
        margin: 5%;
    }
    #sidebar {
        width:100%;
        margin: 0;
        border-bottom: 1px solid #333;
    }
    #passages {
        padding-top: 2em;
        border-left: 0;
    }
}
```
