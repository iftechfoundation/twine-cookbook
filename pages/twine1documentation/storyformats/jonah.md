# Jonah

!!! Warning
    You are reading documentation for Twine 1. This is maintained for archival purposes only.

## Visual Description

This displays the story with black text on a chrome background, and as a player clicks links in the story, the text expands. A player can review earlier passages of the story by scrolling upwards. This approach is called stretch-text.

Players can rewind to past passages to try different choices by simply clicking the links in those passages. (This can be optionally disabled in StorySettings).

The StoryMenu in Jonah is simply the box in the upper-right corner.

## CSS

### Base CSS

```css
#passages {
    position:relative;
    padding-bottom: 12em;
}
.content a {
    color: #4d6ad8;
}
a.internalLink, a.externalLink, a.back, a.return, [data-passage] {
    cursor: pointer;
}
a.brokenLink {
    background-color: red;
    color: black;
}
.marked {
    background-color: pink;
    margin-right: 12px;
}
.marked[title] {
    cursor: help;
}
#floater {
    position: fixed;
    right: 0;
    top: 0;
    z-index: 5;
    background-color: #fff;
}
.toolbar {
    padding: 0;
    visibility: hidden;
}
.toolbar a {
    cursor:pointer;
}
.passage:hover .toolbar {
    visibility: visible;
}
.passage li[data-bullet] {
    list-style-type: none;
}
.passage li[data-bullet]:before {
    content: attr(data-bullet);
    position: relative;
    left: -1em;
}
.toolbar a {
    margin-left: 12px;
}
#storeArea {
    display: none;
}
img {
    vertical-align:bottom;
}
#noscript {
    font-size: 120%;
    font-weight: bold;
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

This CSS completes the default Jonah look-and-feel. This code is removed if "Don't use the Story Format's default CSS" is selected in StorySettings or if the words "blank stylesheet" appear anywhere within a comment in the story's stylesheets.

```css
body {
    font-family: Verdana,sans-serif;
    font-size: 62.5%;
    margin: 0;
    background-color: #f8f8f8;
    color: #303030;
    text-align: center;
}
h1,h2,h3 {
    color: #000;
    font-weight: normal;
    text-align: center;
}
#content1 {
    text-align: left;
}
h1 {
    font-size: 4em;
    line-height: 1.2em;
    margin-bottom: 0;
    margin-top: 1em;
}
h2 {
    font-size: 1.4em;
    font-style: italic;
    margin-top: 1em;
}
h3 {
    font-size: 1.3em;
    margin-bottom: 5em;
    margin-top: .8em;
}
.passage {
    background-color: #f8f8f8;
    font-size: 1.3em;
    line-height: 175%;
    margin-bottom: 2em;
}
.content a {
    font-weight: bold;
    text-decoration: none;
}
.content a:hover {
    text-decoration: underline;
    color: #8ea6ff;
}
.passage:not(:last-child):not(:hover) {
    opacity: 0.4;
    transition: 0.5s;
    -webkit-transition: 0.5s;
}
.passage center {
    max-width:50%;
    margin:auto;
}
input, button {
    font-size: 1.2em;
}
button {
    padding: 0.2em 0.8em;
}
input[type=text] {
    width: 20%;
}
.toolbar a {
    color: #999;
    text-decoration: none;
}
.toolbar a:hover {
    text-decoration: underline;
    color: #8ea6ff;
}
.title {
    color: #000;
    font: bold 1.4em Verdana,sans-serif;
    line-height: 200%;
}
#footer {
    font-size: 1.1em;
    font-style: italic;
    margin-top: 5em;
    text-align: center;
}
#footer a.externalLink {
    border-bottom: 1px solid #464646;
    color: #464646;
    font-weight: normal;
}
#floater {
    border-left: 1px solid #ddd;
    border-bottom: 2px solid #aaa;
    font-size: 1.1em;
    padding: 0 20px;
    text-align: center;
    line-height: 100%;
}
#floater ul {
    text-align: left;
}
#floater a {
    color: #999;
    cursor:pointer;
    font-weight: bold;
    text-decoration: none;
}
#floater a:hover {
    color: #8ea6ff;
    text-decoration: underline;
}
#content1 {
    margin: 0 12.7% 1em 12.7%;
    text-align: left;
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

.toolbar {
    font-size: .5em;
}
.toolbar a {
    margin-left: 12px;
}
.passage ul, .passage ol {
    margin-left: .5em;
    padding-left: 1.5em;
}
li {
    list-style-type: square;
}
```
