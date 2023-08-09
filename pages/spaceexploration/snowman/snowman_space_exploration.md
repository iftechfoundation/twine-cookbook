# "Space Exploration": Snowman (v1.3.0)

## Summary

Games in the [roguelike genre](https://en.wikipedia.org/wiki/Roguelike) often have random events that influence player choices. Frequently, decisions can have lasting impact or even lead to an ending of play in that session or run depending on these random outcomes.

Heavily inspired by [*FTL: Faster Than Light*](https://en.wikipedia.org/wiki/FTL:_Faster_Than_Light) (2012), this example uses the **[`_`.random()](http://underscorejs.org/#random)** function to generate a system of planets consisting of either RED, more risk and more reward, or GREEN, less risk and less reward. Upon entering a system of planets, the player can choose to visit these planets for different outcomes based on a series of choices and an additional use of the **`_`.random()** function. While traveling, the player must also balance the health of the ship, the number of jumps left, and the current fuel that are all displayed using the **[window.story.render()](https://videlais.github.io/snowman/#/1/window_story/functions/render)** function in combination with [Underscore.js templating](http://underscorejs.org/#template).

## Example

[Download](snowman_space_exploration_example.html){: target="_top" download="snowman_space_exploration_example.html"}

## Twee Code

```twee
:: StoryTitle
Space Exploration in Snowman

:: UserScript[script]
// Create a global setup object
window.setup = window.setup || {};

// Add 'variables' object to setup
window.setup.variables = {};
var _vars = window.setup.variables;
_vars.health = 20;
_vars.fuel = 4;
_vars.system = [];
_vars.numberOfJumpsLeft = 10;
  
// Create global functions
window.setup.functions = {};
var _functions = window.setup.functions;
  
_functions.redOutcome = function() {
    var _vars = window.setup.variables;
    var _percentage = _.random(1, 10);
    var response = "";
    if( _percentage >= 6) {
       var _foundHealth = _.random( 1, 5);
       var _foundFuel = _.random( 1, 3);
      response = "The hostile environment damaged the ship, but extra fuel was found. -" + _foundHealth + " to health and +" + _foundFuel + " to fuel.";
        _vars.health -= _foundHealth;
        _vars.fuel += _foundFuel;
  
    } else {

        if( _percentage <= 3) {
          var _foundHealth = _.random(2, 7);
          response = "A hostile ship attacked. -" + _foundHealth + " to health";
         _vars.health -= _foundHealth;
  
      } else {
        response = "Nothing happened."
      }
    }

    return response;
  };
  
  _functions.greenOutcome = function() {
    var _vars = window.setup.variables;
    var _percentage = _.random(1, 10);
    var response = "";
    if( _percentage == 1) {
       var _foundFuel = _.random( 1, 2);
      response = "Fuel was found in some wreckage. + " + _foundFuel + "to fuel";
        _vars.fuel += _foundFuel;
  
    } else {

        if( _percentage >= 6) {
          var _foundHealth = _.random(1, 3);
        response = "During a brief pause, the ship was able to be repaired. +" + _foundHealth + " to health";
         _vars.health += _foundHealth;
  
      } else {
        response = "Nothing happened."
      }
    }

    return response;
  };

:: Start
[[Explore Space|Explore Space 1]]

:: Explore Space 1
<div class="gameScreen">

  <% var _vars = window.setup.variables; %>
  <% _vars.fuel-- %>
  <% _vars.numberOfJumpsLeft-- %>

  [[ Hyperjump |Explore Space 2]]

  <div id="HUD">
    <%= window.story.render("HUD") %>
  </div>

  <%= window.story.render("Generate System") %>

  <div id="display"></div>

  <%= window.story.render("Display System") %>
  
  <%= window.story.render("Check Status") %>

</div>

:: Explore Space 2
<div class="gameScreen">

  <% var _vars = window.setup.variables; %>
  <% _vars.fuel-- %>
  <% _vars.numberOfJumpsLeft-- %>

  [[ Hyperjump |Explore Space 1]]

  <div id="HUD">
    <%= window.story.render("HUD") %>
  </div>

  <%= window.story.render("Generate System") %>

  <div id="display"></div>

  <%= window.story.render("Display System") %>
  
  <%= window.story.render("Check Status") %>

</div>

:: Generate System
<script>
  var _vars = window.setup.variables;
  
  var planets =_.random(1, 4);
  
  _vars.system = new Array(planets);
  
  for(var i = 0; i < _vars.system.length; i++) {
    _vars.system[i] = _.sample(["RED", "GREEN"]);
    }
</script>

:: Display System
<script>
  var _vars = window.setup.variables;

  // Wipe out current contents
  $("#display").html("");
  
  for(var i = 0; i < _vars.system.length; i++) {
  
    if(_vars.system[i] == "RED") {
    var link = $("<a href='#'>RED</a>")
    .click(function(e) {
        $( this )
      .replaceWith( window.story.render("Show Outcome - Red") );
      return false;
    });
    $("#display").append( link );
    $("#display").append( "<br>" );
    }

    if(_vars.system[i] == "GREEN") {
      var link = $("<a href='#'>GREEN</a>")
    .click(function(e) {
        $( this )
      .replaceWith( window.story.render("Show Outcome - Green") );
      return false;
    });
    $("#display").append( link );
    $("#display").append( "<br>" );
    }
  }
  
</script>

:: Show Outcome - Red
<%= window.setup.functions.redOutcome() %>
<% $("#HUD").html(window.story.render("HUD")) %>
<%= window.story.render("Check Status") %>

:: Show Outcome - Green
<%= window.setup.functions.greenOutcome() %>
<% $("#HUD").html(window.story.render("HUD")) %>
 <%= window.story.render("Check Status") %>

:: HUD
Health: <%= window.setup.variables.health %> <br>
Fuel: <%= window.setup.variables.fuel %> <br>
Number of Jumps Left: <%= setup.variables.numberOfJumpsLeft %> <br>

:: Destroyed
The ship exploded in flight.

<h3>Game Over</h3>

:: Lost in space
Without fuel, the ship tumbled and spun in the endless black.

<h3>Game Over</h3>

:: Safe
After 10 hyperjumps, the ship left the hazardous area and called for help.

<h3>Success!</h3>

:: Check Status
<script>

  var _vars = window.setup.variables;

  var status = "";

  if(_vars.health <= 0) {
    status = window.story.render("Destroyed");
  }
  if(_vars.fuel <= 0) {
    status = window.story.render("Lost in space");
  }
  if(_vars.numberOfJumpsLeft <= 0) {
    status = window.story.render("Safe");
  }
  
  if(status != "") {
    $(".gameScreen").html(status);
  }
</script>

```

[Twee Download](snowman_space_exploration_twee.txt){ target="_top" download="snowman_space_exploration_twee.txt"}
