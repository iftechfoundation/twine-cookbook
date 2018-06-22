# "Limiting the range of a number": Harlowe (v2.0)

## Summary

This recipe demonstrates how to limit a numeric variable to a value between a set range, this process is commonly known as **clamping**.

The example adds a *clamp()* function to the existing built-in [*Math*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math) global JavaScript object, which can then be called to achieve the desired result.

<div class="alertbox information"><strong>Note:</strong> The example also adds a *clamp()* function to the built-in [*Number*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) global JavaScript object which the new *Math.clamp()* function uses internally, **however** due to how Harlowe implements variables the *<Number>.clamp()* function can't be used directly within a [*(set:)*](https://twine2.neocities.org/#macro_set) macro.</div>


## Live Example

<section>
<iframe src="harlowe_clamping_numbers_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_clamping_numbers_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Limiting the range of a number in Harlowe


:: UserScript [script]
(function () {

	/*
		Returns the number clamped to the specified bounds.

		WARNING:
			Due to how Harlowe implements variables you can NOT call this function directly,
			you must use the Math.clamp() function instead.
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
			(set: $variable to Math.clamp($variable, 1, 10))

			→ Limit result of mathematical operation to a value between 1 and 10 inclusive.
			(set: $variable to Math.clamp($variable + 5, 1, 10)_
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
Initialise the numeric variable to a value with the range you want.
eg. between ''1'' and ''10'' inclusive.
&#40;note: You don't need to use the //Math.clamp()// funtion at this point.&#41;\

(set: $valueToClamp to 5)
''Current value'': $valueToClamp

Increase the number to a value that is ''within'' the desired range.
eg. Add 1 to the current value.\

(set: $valueToClamp to Math.clamp($valueToClamp + 1, 1, 10))
''New value'': $valueToClamp

Try to increase the number to a value that is ''outside'' the desired range.
eg. Add 100 to the current value.\

(set: $valueToClamp to Math.clamp($valueToClamp + 100, 1, 10))
''New value'': $valueToClamp

Decrease the number to a value that is ''within'' the desired range.
eg. Minus 5 from the current value.\

(set: $valueToClamp to Math.clamp($valueToClamp - 5, 1, 10))
''New value'': $valueToClamp

Try to decrease the number to a value that is ''outside'' the desired range.
eg. Minus 100 from the current value.\

(set: $valueToClamp to Math.clamp($valueToClamp - 100, 1, 10))
''New value'': $valueToClamp

```

Download: <a href="harlowe_clamping_numbers_twee.txt" target="_blank">Twee Code</a>

