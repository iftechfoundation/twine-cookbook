# "Arrays": Snowman (v1.3)

## Summary

You can use [arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) to create collections of values, like inventories. Arrays are a special type of data that can hold multiple other values. Each value in an array is assigned an *index*, which is a number that corresponds to the position of that item or element in the array. In SugarCube and JavaScript, arrays are *zero-based*, meaning the first element in the array is given the index `0`. Arrays have many built-in methods and other features for your use. You can create an array by assigning a variable to the array literal, which is a pair of brackets (`[]`): `<% s.myArray = [] %>`.

You can [access specific elements](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Accessing_array_elements) in an array by following it's variable name with a pair of brackets containing the index you want to check, e.g. `s.myArray[1]` would point to the second element in the array. You can test whether an array contains an element using the [*Array#includes()* method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes), and add new items using the [*Array#push()* method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push). You can also join separate arrays together (called *concatenation*, meaning adding end-to-end) using the method [*Array#concat()*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat).

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
