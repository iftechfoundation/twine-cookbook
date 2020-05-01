# *tags()*

Has a value equal to an array containing the current passage's tags. The meaning of "current passage" is the same as it is for *passage()*. Since this is a Javascript array, you will need to use built-in array functions to obtain values from it. Usually, you'd simply want to do something like this:

```twee
<<if tags().indexOf("thunder") > -1>>\
Thunder is crackling above!
<<endif>>\
```
