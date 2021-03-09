# "Limiting the Range of a Number": Chapbook (v1.0.0)

## Summary

This example demonstrates how to limit a numeric variable to a value between a set range. This process is commonly known as clamping.

The example adds a **clamp()** function to the existing built-in **[Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)** global JavaScript object, which can then be called to achieve the desired result.

This added function is then used within the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) to set a value before using an expression to show its value within the passage itself.

## Example

[Download](chapbook_clamping_numbers_example.html){: target="_top" download="chapbook_clamping_numbers_example.html"}

## Twee Code

```twee
:: StoryTitle
Chapbook: Limiting Range of Number

:: UserScript[script]
(function () {

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
      example: Math.clamp(variable, 1, 10)

      → Limit result of mathematical operation to a value between 1 and 10 inclusive.
      variable: Math.clamp(variable + 5, 1, 10)
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
exampleNumber: 11
exampleResult: Math.clamp(exampleNumber, 1, 10)
--

Despite *exampleNumber* being {exampleNumber}, it will be "clamped" to the highest number given to the function (10). The result is {exampleResult}.

```

[Twee Download](chapbook_clamping_numbers_twee.txt){ target="_top" download="chapbook_clamping_numbers_twee.txt"}
