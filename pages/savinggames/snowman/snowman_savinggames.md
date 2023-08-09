# "Saving Games": Snowman (v1.3.0)

## Summary

Snowman provides the **[window.story.saveHash()](https://videlais.github.io/snowman/#/1/window_story/functions/saveHash)** and **[window.story.restore()](https://videlais.github.io/snowman/#/1/window_story/functions/restore)** functions to produce a hash of the current story state and then recover it. However, it does not provide a mechanism for saving the hash between sessions. Through using the *[window.localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)* global variable, this can be accomplished.

## Example

[Download](snowman_savinggames_example.html){: target="_top" download="snowman_savinggames_example.html"}

## Twee Code

```twee
:: StoryTitle
Saving Games in Snowman

:: UserScript[script]
window.storage = {
  ok: function() {
    try {
        var storage = window["localStorage"],
          x = '__storage_test__';
        storage.setItem(x, x);
        storage.removeItem(x);
        return true;
      }
      catch(e) {
        return e instanceof DOMException && (
        // everything except Firefox
        e.code === 22 ||
        // Firefox
        e.code === 1014 ||
        // test name field too, because code might not be present
        // everything except Firefox
        e.name === 'QuotaExceededError' ||
        // Firefox
        e.name === 'NS_ERROR_DOM_QUOTA_REACHED') &&
        // acknowledge QuotaExceededError only if there's something already stored
        storage.length !== 0;
      }
  },
  save: function(hash) {
    window.localStorage.setItem('hash', hash);
  },
  restore: function() {
    return window.localStorage.getItem('hash');
  },
  delete: function() {
    window.localStorage.removeItem("hash");
  }
}

:: Start
<%
  if(window.storage.ok()) { %>
  Window storage works!
<% } %>  
<%
  if(window.storage.restore()) { %>
  There is a session saved!
<% } %>
[[Save the session hash?]]

[[Restore from previous session?]]

[[Delete previous session?]]

:: Save the session hash?
The hash is <%= window.story.saveHash() %>. It has been saved!

<% if(window.storage.ok()) {
  window.storage.save(window.story.saveHash())
}%>

[[Go back?|Start]]

:: Restore from previous session?
<% if(window.storage.ok()) {
  if(window.story.restore(window.storage.restore()) ) { %>
  The restore was successful!
<% }
}
%>

[[Go back?|Start]]

:: Delete previous session?
<% window.storage.delete() %>

[[Go back?|Start]]
```

[Twee Download](snowman_savinggames_twee.txt){ target="_top" download="snowman_savinggames_twee.txt"}
