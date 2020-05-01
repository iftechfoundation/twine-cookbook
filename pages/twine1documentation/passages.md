# Passages

!!! Warning
    You are reading documentation for Twine 1. The latest version is Twine 2, and very little functionality is backwards compatible.

## Introduction

The basic narrative unit of a book is a chapter. Although there are books that don't divide themselves up into chapters, most do, and it's a useful way for writers and readers to keep track of a book's structure. The corresponding unit for hypertext is a choice and the text that leads to it. In Choose Your Own Adventure books, this unit was a single printed page:

> If you decide to explore the ledge where the Seeker has come to rest, turn to page 6.
>
> If you decide to cut loose from the Maray and dive with the Seeker into the canyon in the ocean floor, turn to page 4.
>
> (R. A. Montgomery, Journey Under the Sea)

As these books became more complex, more pages were required – and some of these pages didn't need to be terribly long. Gamebooks like the Fighting Fantasy series began to use numbered passages, several of which might be printed on a single page:

> You hear the sound of running feet approaching rapidly; you cannot yet see who or what is coming. Will you run through the nearest archway (turn to 17), or hold your ground and draw your sword (turn to 30)?
>
> (Steve Jackson, Talisman of Death)

Using numbers to keep track of what to read next made sense for readers who had to locate the next part of the story themselves. But when hypertext leapt onto computer screens, choices could be made just by clicking underlined text:

> Scholar and showman, Urquhart knew in all his most sensitive bones that __this was the time__. There was a furious logic to this day-after-the-day, a logic he would have recognized even without Tate's nudge and a wink and "my friends around the Beltway" over lunch.
>
> He could feel the timing. He could feel a lot of things. Something had been at work in the world, some wavefront of rapid change only dimly felt but no less powerful for that. The waves passed through everything and everyone, transforming as they went. You only had to check the mirror.
>
>(Stuart Moulthrop, Victory Garden)

There have been many names for these individual parts of text that readers navigate through. In Twine, they are known as passages, a word that both means a section of a written work as well as a route one might pass through.

## Details

In Twine, passages are distinguished by their title. Passage titles are case-sensitive, which means that “This door” and “THIS DOOR” are two different passages. They also cannot contain the “]” and “|” symbols, or any line breaks. Passage titles must also be unique - trying to give two passages the same name will, usually, fail.

Passages may also possess one or more tags. Consult the tags article to learn more about them.

Passages are usually drawn in the Story Map with blue title bars. Terminus passages - passages which contain no links leading out of them - are drawn with a darker title. The Start passage is drawn with a green bar.
