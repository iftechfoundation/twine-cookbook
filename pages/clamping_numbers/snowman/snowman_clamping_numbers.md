# "Limiting the Range of a Number": Snowman (v1.3)

## Summary

This example demonstrates how to limit a numeric variable to a value between a set range, this process is commonly known as clamping.

The example adds a **clamp()** function to the existing built-in [**Math**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math) global JavaScript object, which can then be called to achieve the desired result. It also adds a **clamp()** function to the built-in [**Number**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) global JavaScript object that the new *Math.clamp()* function uses internally.

## Example

[Download](snowman_clamping_numbers_example.html){: target="_top" download="snowman_clamping_numbers_example.html"}

## Twee Code

```twee
:: StoryTitle
Limiting the range of a number in Snowman


:: UserScript [script]
(function () {

  /*
    Returns the number clamped to the specified bounds.

    Usage:
      → Limit numeric variable to a value between 1 and 10 inclusive.
      <% s.variable = s.variable.clamp(1, 10) %>
  */
  Object.defineProperty(Number.prototype, 'clamp', {
    configurable : true,
    writable     : true,

    value(/* min, max */) {
      if (this == null) { // lazy equality for null
        throw new TypeError('Number.prototype.clamp called on null or undefined');
      }

      if (arguments.length !== 2) {
        throw new Error('Number.prototype.clamp called with an incorrect number of parameters');
      }

      var min = Number(arguments[0]);
      var max = Number(arguments[1]);

      if (min > max) {
        var tmp = min;
        min = max;
        max = tmp;
      }

      return Math.min(Math.max(this, min), max);
    }
  });


  /*
    Returns the given numerical clamped to the specified bounds.

    Usage:
      → Limit numeric variable to a value between 1 and 10 inclusive.
      <% s.variable = Math.clamp(s.variable, 1, 10) %>

      → Limit result of mathematical operation to a value between 1 and 10 inclusive.
      <% s.variable = Math.clamp(s.variable + 5, 1, 10) %>
  */
  Object.defineProperty(Math, 'clamp', {
    configurable : true,
    writable     : true,

    value(num, min, max) {
      var value = Number(num);
      return Number.isNaN(value) ? NaN : value.clamp(min, max);
    }
  });

})();


:: Start
Initialize the numeric variable to a value with the range you want.<br>
eg. between <b>1</b> and <b>10</b> inclusive.<br>
&#40;note: You don't need to use the <i>Math.clamp()</i> function at this point.&#41;<br>

<% s.valueToClamp = 5 %>
<b>Current value</b>: <%= s.valueToClamp %>

Increase the number to a value that is <b>within</b> the desired range.<br>
eg. Add 1 to the current value.

<% s.valueToClamp = Math.clamp(s.valueToClamp + 1, 1, 10) %>
<b>New value</b>: <%= s.valueToClamp %>

Try to increase the number to a value that is <b>outside</b> the desired range.<br>
eg. Add 100 to the current value.

<% s.valueToClamp = Math.clamp(s.valueToClamp + 100, 1, 10) %>
<b>New value</b>: <%= s.valueToClamp %>

Decrease the number to a value that is <b>within</b> the desired range.<br>
eg. Minus 5 from the current value.

<% s.valueToClamp = Math.clamp(s.valueToClamp - 5, 1, 10) %>
<b>New value</b>: <%= s.valueToClamp %>

Try to decrease the number to a value that is <b>outside</b> the desired range.<br>
eg. Minus 100 from the current value.

<% s.valueToClamp = Math.clamp(s.valueToClamp - 100, 1, 10) %>
<b>New value</b>: <%= s.valueToClamp %>

```

[Twee Download](snowman_clamping_numbers_twee.txt){ target="_top" download="snowman_clamping_numbers_twee.txt"}
