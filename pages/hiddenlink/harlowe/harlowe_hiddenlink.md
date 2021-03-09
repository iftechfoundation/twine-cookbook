# "Hidden Link": Harlowe (v2.0)

## Summary

"Hidden Link" demonstrates how to create a 'hidden' link that is only revealed when the cursor passes over it.

Using CSS and JavaScript, a rule is created for transparent color and applied or removed through using jQuery's **[on()](http://api.jquery.com/on/)** function with 'mouseenter' and 'mouseleave' events.

The use of a "footer" special Passage is also used to run the required JavaScript after each passage is displayed.

Harlowe supports a number of different techniques for creating links and the resulting HTML elements generated is different for each of these techniques. The generated HTML falls into two main groups: those that include a `<<tw-link>>` element, and those that include a ".enchantment-link" classed element. This example supports both groups.

## Example

[Download](harlowe_hiddenlink_example.html){ target="_top" download="harlowe_hiddenlink_example.html"}

## Twee Code

```twee
:: StoryTitle
Harlowe: Hidden Link


:: UserStylesheet [stylesheet]
.hidden tw-link, .hidden .enchantment-link {
  color: transparent;
}

tw-include[title="Hidden Link Setup"] {
  display: none;
}


:: Hidden Link Setup [footer]
<script>
  /*
    Hidden links that are always hidden:
      <span class="hidden">[[A hidden link]]</span>
  */
  $('.hidden')
    .addClass('hidden');

  /*
    Hidden links that hide unless you're hovering over them:
      <span class="hides">[[A hidden link]]</span>
  */
  $('.hides')
    .addClass('hidden')
    .on('mouseenter', function () {
      $(this).removeClass('hidden');
    })
    .on('mouseleave', function () {
      $(this).addClass('hidden');
    });

  /*
    Hidden links that reveal themselves when you hover over them:
      <span class="reveals">[[A hidden link]]</span>
  */
  $('.reveals')
    .addClass('hidden')
    .one('mouseenter', function () {
      $(this).removeClass('hidden');
    });
</script>


:: Start
''Examples of tw-link element based links''

A hidden link that's always hidden: <span class="hidden">[[A hidden link]]</span>

A hidden link that hides unless you're hovering over it: <span class="hides">[[A hidden link]]</span>

A hidden link that reveals itself when you hover over it: <span class="reveals">[[A hidden link]]</span>


''Examples of .enchantment-link CSS class based links''

A hidden link that's always hidden: <span class="hidden">[A hidden link]<link|</span>

A hidden link that hides unless you're hovering over it: <span class="hides">[A hidden link]<link|</span>

A hidden link that reveals itself when you hover over it: <span class="reveals">[A hidden link]<link|</span>

(click: ?link)[(go-to: "A hidden link")]


:: A hidden link
You found it!


```

[Twee Download](harlowe_hiddenlink_twee.txt){ target="_top" download="harlowe_hiddenlink_twee.txt"}
