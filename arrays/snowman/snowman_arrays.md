# "Arrays": Snowman (v1.3)

## Summary

[Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) are a collection of values. Each value in an array is assigned an *index*, which is a number that corresponds to the position of that item or element in the array. In JavaScript, arrays are *zero-based*, meaning the first element in the array is given the index `0`. Arrays have many built-in methods and other features for your use. You can create an array by assigning a variable to the array literal, which is a pair of brackets (`[]`): `<% s.myArray = [] %>`.

[Specific elements](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Accessing_array_elements) can be accessed in an array by following its variable name with a pair of brackets containing the index to check. Testing whether an array contains an element can be done using the [*Array#includes()* function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes); adding new items can be doone using the [*Array#push()* function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push).

## Live Example

<section>
<iframe src="snowman_arrays_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_arrays_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Arrays in Snowman

:: UserScript [script]
(function () {
    var s = window.story.state;
    s.inventory = [];
    s.chest = ['a shield', 'a suit of armor'];
    s.chestOpen = false;
}());

:: Header
You are currently carrying: 
<% if (s.inventory.length === 0) { %>
nothing.
<% } else { %>
<%= s.inventory.join(', ') + '.' %>
<% } %>

:: Start
<%= window.story.render("Header") %><hr />

You find yourself inside a small room. In the corner, you see a sword, and decide to pick it up.

<% s.inventory.push('a sword') %>
[[Continue|hallway]]

:: hallway
<%= window.story.render("Header") %><hr />
You see a chest here in the hallway.
<% if (!s.chestOpen) { %>
Do you want to open it?

[[Open the chest.|chest]]
<% } else { %>
It's open, and there's nothing inside.
<% } %>

[[Move on.|dart trap]]

:: chest
<% s.inventory = s.inventory.concat(s.chest) %>
<% s.chestOpen = true %>
<%= window.story.render("Header") %><hr />

You open the chest and find <%= s.chest.join(' and ') %>.

[[Okay.|hallway]]

:: dart trap
<%= window.story.render("Header") %><hr />
Several darts shoot out of a wall at you!
<% if (s.inventory.includes('a shield')) { %>

Luckily, your shield will protect you.
<% } else { %>

With no way to defend yourself, you die.
<% } %>
```

Download: <a href="snowman_arrays_twee.txt" target="_blank">Twee Code</a>
