# "Player Statistics": Snowman (v1.3.0)

!!! Information
    Elements must exist *before* the attempt to bind to them in order to be successful. This example uses the [**ready()**](https://api.jquery.com/ready/) function to achieve this with the first, starting passage.

## Summary

One of the most popular mechanics of table-top role-playing games are those where the player must determine their in-game statistics and then use them to make decisions.

In this example, the jQuery event handler **[click()](https://api.jquery.com/click/)** is used to bind to multiple buttons. Depending on what was clicked, the content is replaced or values adjusted based on if a conditional statement is true. Values are then tested when combined with a [random number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) between 1 to 6, mimicking a common 1d6 mechanic to check if a value is above a target number.

## Example

[Download](snowman_player_statistics_example.html){: target="_top" download="snowman_player_statistics_example.html"}

## Twee Code

```twee
:: StoryTitle
Player Statistics in Snowman

:: UserScript[script]
$(function() {

  // Create a global setup object
  window.setup = window.setup || {};

  // Create a global propety on the setup object
  window.setup.stats = {};

  // Create (and overwrite) the use of 's'
  var s = window.setup.stats;

  s.empathy = 10;
  s.intelligence = 10;
  s.totalPoints = 5;

  $("#empathyIncrease").click(function(){
    if(s.totalPoints > 0) {
      setup.stats.empathy++;
      s.totalPoints--;
      $("#empathyStat").text(s.empathy);
      $("#pointsStat").text(s.totalPoints);
    }
  });

  $("#empathyDecrease").click(function(){
    if(s.empathy > 0) {
      s.empathy--;
      s.totalPoints++;
      $("#empathyStat").text(s.empathy);
      $("#pointsStat").text(s.totalPoints);
    }
  });

  $("#intelligenceIncrease").click(function(){
    if(s.totalPoints > 0) {
      s.intelligence++;
      s.totalPoints--;
      $("#intelligenceStat").text(s.intelligence);
      $("#pointsStat").text(s.totalPoints);
    }
  });

  $("#intelligenceDecrease").click(function(){
    if(s.intelligence > 0) {
      s.intelligence--;
      s.totalPoints++;
      $("#intelligenceStat").text(s.intelligence);
      $("#pointsStat").text(s.totalPoints);
    }
  });

  $("#pointsReset").click(function(){
    s.empathy = 10;
    s.intelligence = 10;
    s.totalPoints = 5;
    $("#empathyStat").text(s.empathy);
    $("#intelligenceStat").text(s.intelligence);
    $("#pointsStat").text(s.totalPoints);
  });

  // Add a randomInt function to the Math global
  Math.randomInt = function(min, max) {
    min = Math.ceil(min);
    max = Math.floor(max);
    return Math.floor(Math.random() * (max - min)) + min;
  };

  $("#testIntelligence").click(function() {

    var result = s.intelligence + Math.randomInt(1,6);

    if(result >= 15) {
      $("#intelligenceResult").text("Success! (" + result + " >= 15)");
    } else {
      $("#intelligenceResult").text("Failure! (" + result + " < 15)");
    }

    console.log("Test!");
  });

  $("#testEmpathy").click(function() {

    var result = s.empathy + Math.randomInt(1,6);

    if(result >= 15) {
      $("#empathyResult").text("Success! (" + result + " >= 15)");
    } else {
      $("#empathyResult").text("Failure! (" + result + " < 15)");
    }

  });


});

:: Start
Empathy: <button id="empathyIncrease">[+]</button> <button id="empathyDecrease">[-]</button>

Intelligence: <button id="intelligenceIncrease">[+]</button> <button id="intelligenceDecrease">[-]</button>

<button id="pointsReset">[Reset Points]</button>

Empathy: <span id="empathyStat">10</span>

Intelligence: <span id="intelligenceStat">10</span>

Remaining Points: <span id="pointsStat">5</span>

<button id="testIntelligence">Make an intelligence check?</button>
<div id="intelligenceResult"></div>

<button id="testEmpathy">Make an empathy check?</button>
<div id="empathyResult"></div>

```

[Twee Download](snowman_player_statistics_twee.txt){ target="_top" download="snowman_player_statistics_twee.txt"}

## See Also

[Conditional Statements](../../conditionalstatements/snowman/snowman_conditionalstatements.md), [Setting and Showing](../../settingandshowing/snowman/snowman_settingandshowing.md)
