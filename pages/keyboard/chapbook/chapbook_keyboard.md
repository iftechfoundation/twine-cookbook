# "Keyboard Events": Chapbook (v1.0.0)

## Summary

"Keyboard Events" demonstrates how to capture [keyboard events](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent) and then how to associate individual keys with activities within a story.

The example uses **[addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)** to monitor for all ["keyup" events](https://developer.mozilla.org/en-US/docs/Web/Events/keyup). Once a "keyup" event has occurred, two values are available:

* The *keyCode* property: the numerical value representing the key presented in its [decimal ASCII code](http://www.asciichart.com/) supported by effectively all browsers.
* The *key* property: the string value of the key presented supported by most modern web-browsers.

## Example

[Download](chapbook_keyboard_example.html){: target="_top" download="chapbook_keyboard_example.html"}

## Twee Code

```twee
:: StoryTitle
Chapbook: Keyboard

:: UserScript[script]
(function () {
  document.addEventListener('keyup', function (ev) {
    /* the ev variable contains a keyup event object.
     *
     * ev.keyCode - contains the ASCII code of the key that was released, this property is supported in effectively all browsers.
     * ev.key     - contains the key value of the key that was released, this property is supported by most modern browsers.
     *
     */

    /* the following shows an alert when the 'a' key is released. */
    if (ev.key === 'a') {
      alert("the 'a' key was released.");
    }
  });
}());


:: Start
Press and release the ''a'' key to show an Alert dialog.

```

[Twee Download](chapbook_keyboard_twee.txt){ target="_top" download="chapbook_keyboard_twee.txt"}
