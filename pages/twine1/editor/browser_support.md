# Browser Support

The Twine 1.4+ runtime engine (that is, the Javascript engine used to play built Twine games) has the following official browser support:

| Browser                                               | Basic Usage  | Embedded Images | HTML5-based history             | CSS Transitions |
| ----------------------------------------------------- | ------------ | --------------- | ------------------------------- | --------------- |
| IE 7                                                  | Will not run |                 |                                 |                 |
| IE 8                                                  | ✔            | \< 32KB each    |                                 |                 |
| IE 9                                                  | ✔            | ✔               |                                 |                 |
| IE 10+                                                | ✔            | ✔               | ✔                               | ✔               |
| Current versions of desktop Chrome, Firefox and Opera | ✔            | ✔               | ✔                               | ✔               |
| Safari 5.1+                                           | ✔            | ✔               | ✔                               | ✔               |
| iOS Safari 6+                                         | ✔            | ✔               | Only if private browsing is off | ✔               |

Other browsers are not officially supported. Their adherence to these
features is unknown.

## HTML5 history fallback

Since IE 8 and IE 9 do not support HTML5 History, they will fallback to the old hashstring-based history method used in Twine 1.3.5. Every time the player changes passages, a new hashstring containing an encoding of the current game state is added to the page's URL. This creates a new entry in the browser's history, and allows the back button to return to previous passages. However, it is bug-prone: whenever the back button is used, the entire page is reloaded and the game state is re-computed from the hash. This may cause certain custom macros (such as audio macros) to fail.
