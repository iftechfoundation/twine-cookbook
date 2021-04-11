# "Storylets": Harlowe (v3.2)

## Summary

Storylets are [a different way of approaching nonlinear storytelling](https://emshort.blog/2019/11/29/storylets-you-want-them/). Instead of linking from one passage to another in Twine, storylets are defined by what are called its *requirements* and *content*.

The metaphor of a deck of cards is often useful in understanding storylets. A card is able to be drawn from a deck if its requirements are met. Through defining many cards (passages in Twine) and conditions under which they can be used (their requirements), dynamic storytelling can take place as different arrangements become possible through writing simple rules for each card.

The [`(storylet:)` macro](https://twine2.neocities.org/#macro_storylet) defines a passage as a storylet in Harlowe. It should appear as either the first line or as near to the top of the passage as possible. The value used with the `(storylet:)` macro defines if it is "open" or not. Harlowe uses a [`when` lambda](https://twine2.neocities.org/#type_lambda) to define these, and a storylet is considered "open" when its lambda value evaluates to true when comparing two values or variables.

The [`(link-storylet:)` macro](https://twine2.neocities.org/#macro_link-storylet) selects the first open storylet based on a number passed to the macro. To access the fourth open storylet, for example, `(link-storylet: 4)` could be used. If no storylets are open, a third value can be used in the format of `(link-storylet: 4, "No storylets")` where the fourth open storylet would be used or the value "No storylets" shown to the user if no storylets were available when it checked.

In this example, two passages use the `(storylet:)` macro. One, "Joy Ewers" has a requirement of `$type` being equal to "Hookup". The other passage using the `(storylet:)` macro is "Rhys Johns", which has a requirement of `$type` being equal to "Causal Dating". Depending on the value of `$type`, set in the "Start" passage using the [`(cycling-link:)` macro](https://twine2.neocities.org/#macro_cycling-link), either one or the other will be open and picked by the use of the `(link-storylet:)` macro. Revisiting the "Start" passage allows for changing the value of `$type` and which storylet is open, changing possible navigation through the story.

## Example

[Download](harlowe_storylets_example.html){: target="_top" download="harlowe_storylets_example.html"}

## Twee Code

```twee
:: StoryTitle
Harlowe: Storylets

:: StoryData
 {
  "ifid": "D709A2F4-0E88-4010-B157-8ADEDDB2DC74",
  "format": "Harlowe",
  "formatVersion": "3.2.1",
  "zoom": "1",
  "start": "1"
}

:: Start {"position":"199,99","size":"100,100"}
You open the app and wait for it to load. You have never liked dating apps, but agreed to try this new one to get your friend to stop bugging you about it

You stare at the prompt on the screen.

//What are you looking for? (Click to change)//
(cycling-link: bind $type, "Hookup", "Casual Dating")

[[Matches]]

:: Matches {"position":"198,299","size":"100,100"}

(link-storylet: 1)

:: Send message? {"position":"407,402","size":"100,100"}
You send a message and close the app for now.

:: Rhys Johns {"position":"705,229","size":"100,100"}
(storylet: when $type is "Casual Dating")

''Name:'' Rhys Johns

''Pronouns:'' He/Him

[[Send message?]]

[[Change search?->Start]]

:: Joy Ewers {"position":"432,204","size":"100,100"}
(storylet: when $type is "Hookup")

''Name:'' Joy Ewers

''Pronouns:'' They/Them

[[Send message?]]

[[Change search?->Start]]

```

[Twee Download](harlowe_storylets_twee.txt){ target="_top" download="harlowe_storylets_twee.txt"}
