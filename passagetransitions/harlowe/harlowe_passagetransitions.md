# "Passage Transitions": Harlowe (v3.0)

## Summary

When using the [*(transition-arrive:)*](https://twine2.neocities.org/#macro_transition-arrive) or [*(transition-depart:)*](https://twine2.neocities.org/#macro_transition-depart) macros with links, the resulting transition effect will be shown to the player upon activating the link (depart) or as it is shown (arrive).

Possible transition effects include:
* "instant" (causes the passage to instantly vanish)
* "dissolve" (causes the passage to gently fade out)
* "flicker" (causes the passage to roughly flicker in - don't use with a long (transition-time:)))
* "shudder" (causes the passage to disappear while shaking back and forth)
* "rumble" (causes the passage to instantly appear while shaking up and down)
* "slide-right" (causes the passage to slide in from the right)
* "slide-left" (causes the passage to slide in from the left)
* "pulse" (causes the passage to disappear while pulsating rapidly)

## Live Example

<section>
<iframe src="harlowe_passagetransitions_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_passagetransitions_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Harlowe 3: Passage Transitions

:: Start
(transition-depart: "dissolve")[[Dissolve Passage]]

:: Dissolve Passage
(transition-arrive: "slide-right")[[Slide-right Passage]]

:: Slide-right Passage
Double-click this passage to edit it.

```

Download: <a href="harlowe_passagetransitions_twee.txt" target="_blank">Twee Code</a>
