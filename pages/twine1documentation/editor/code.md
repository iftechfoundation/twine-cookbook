# Code

Using only text, many stories can be created! However, how would the following example be created?

> As you reach the door you hear the crash of a giant stone slab as it falls from the ceiling. Turning around, you see that your exit is now blocked. If you have a Silver Key, you may try to open the door by turning to 158.
>
> If you do not possess a Silver Key, turn to 259.
>
> (Joe Dever, *Flight from the Dark*)

Readers could be asked to click a link, but having the story remember would be better. Using code helps with this!

In Twine, *code* takes the form of macros the story's text. These are set off by double angle brackets, `<<like this>>`, in a manner resembling HTML tags. When a passage is displayed, the macro invocation is not displayed; instead, its code runs. For example, this source code would produce something akin to the text quoted above:

```twee
As you reach the door you hear the crash of a giant stone slab as it falls from the ceiling. Turning around, you see that your exit is now blocked.
<<if $hasSilverKey>>\
  * [[Open the door with your key]]
<<else>>\
  * [[Try to force the door open]]
<<endif>>
```
