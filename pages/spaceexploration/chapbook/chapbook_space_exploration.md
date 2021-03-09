# "Space Exploration": Chapbook (v1.0.0)

## Summary

Games in the [rogue-like genre](https://en.wikipedia.org/wiki/Roguelike) often have random events that influence player choices. Frequently, decisions can have lasting impact or even lead to an ending of play in that session or run depending on these random outcomes.

Heavily inspired by [*FTL: Faster Than Light*](https://en.wikipedia.org/wiki/FTL:_Faster_Than_Light) (2012), this example generates a system of four planets consisting of either RED, more risk and more reward, or GREEN, less risk and less reward. Upon entering a system of planets, the player can "Scan System" and then choose to visit these planets for different outcomes based on a series of choices and the use of the **[Math.random()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random)** function. At the same time, the player must also balance the health of the ship, the number of jumps left, and the current fuel. These are displayed when visiting the "Statistics" passage. If any of them drop below 0, the game ends with an ending matching that statistic.

This example uses a complex combination of the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html), [`[JavaScript]`](https://klembot.github.io/chapbook/guide/advanced/using-javascript-in-passages.html) modifier, and internal JavaScript functionality in Chapbook, including the use of the function **window.go()**.

## Example

[Download](chapbook_space_exploration_example.html){: target="_top" download="chapbook_space_exploration_example.html"}

## Twee Code

```twee

:: StoryTitle
Chapbook: Space Exploration

:: UserScript[script]
// Add a randomRange
// Used from https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random
Math.randomRange = (min, max) => {
    min = Math.ceil(min);
    max = Math.floor(max);
    return Math.floor(Math.random() * (max - min)) + min;
};

:: Start
health: 20
fuel: 4
system: []
numberOfJumpsLeft: 10
--
{embed passage: 'GenerateSystem'}

[[Explore Space]]

:: Explore Space
{embed passage: "CheckStatus"}
Current System:
{embed passage: 'DisplaySystem'}
<hr>
[[Hyperjump]]
  
[[Statistics]]

:: GenerateSystem
[JavaScript]

  // There will always be four (4) planets
  let planets = 4;
  
  // Reset global system
  let system = engine.state.get('system');
  system = [];
  
  // Add 0 (Red) or 1 (Green) planets
  for(let i = 0; i < planets; i++) {
    // Get a random number from 0 to 2
    // 0 = RED
    // 1 = GREEN
    // 2 = EMPTY
    system.push(Math.randomRange(0,3));
  }
  
  // Update the new 'system'
  engine.state.set('system', system);



:: CheckStatus
[JavaScript]
  let health = engine.state.get("health");
  let fuel = engine.state.get("fuel");
  let numberOfJumpsLeft = engine.state.get("numberOfJumpsLeft");

  if(health <= 0) {
    // Introduce a micro-delay before transition
    setTimeout(() => {
      go("Destroyed");
    }, 10);
  }

  if(fuel <= 0) {
    // Introduce a micro-delay before transition
    setTimeout(() => {
      go("Lost in Space");
    }, 10);
  }

  if(numberOfJumpsLeft <= 0) {
    // Introduce a micro-delay before transition
    setTimeout(() => {
      go("Safe");
    }, 10);
  }



:: Destroyed
The ship exploded in flight.

Game Over.

:: Lost in Space
Without fuel, the ship tumbled and spun in the endless black.

Game Over

:: Safe
After 10 hyperjumps, the ship left the hazardous area and called for help.

Success!

:: Hyperjump
fuel: fuel - 1
numberOfJumpsLeft: numberOfJumpsLeft - 1
--
{embed passage: "CheckStatus"}
{embed passage: "GenerateSystem"}
  
[[Scan System->Explore Space]]


:: DisplaySystem
[if system[0] == 0]
  {reveal link: 'RED', passage: 'RED'}
[if system[0] == 1]
  {reveal link: 'GREEN', passage: 'GREEN'}
[if system[0] == 2]
  <br>
[if system[1] == 0]
  {reveal link: 'RED', passage: 'RED'}
[if system[1] == 1]
  {reveal link: 'GREEN', passage: 'GREEN'}
[if system[1] == 2]
  <br>
[if system[2] == 0]
  {reveal link: 'RED', passage: 'RED'}
[if system[2] == 1]
  {reveal link: 'GREEN', passage: 'GREEN'}
[if system[2] == 2]
  <br>
[if system[3] == 0]
  {reveal link: 'RED', passage: 'RED'}
[if system[3] == 1]
  {reveal link: 'GREEN', passage: 'GREEN'}
[if system[3] == 2]
  <br>


:: RED
REPORT
[JavaScript]

  let percentage = Math.randomRange(0, 11);
  let foundHealth;
  let foundFuel;
  let health = engine.state.get('health');
  let fuel = engine.state.get('fuel');
  
  if(percentage >= 6) {
  
    foundHealth = Math.randomRange(1, 6);
    foundFuel = Math.randomRange(1, 3);

    write(`The hostile environment damaged the ship, but extra fuel was found. (-${foundHealth} to health and +${foundFuel} to fuel.)`);

    health -= foundHealth;
    fuel += foundFuel;

  }
  
  if(percentage >= 3 && percentage < 6) {
  
      foundHealth = Math.randomRange(2, 8);

      write(`A hostile ship attacked. (-${foundHealth} to health)`);

      health -= foundHealth;
  
  }
  
  if(percentage < 3) {
    write("Nothing happened.");
  }
  
  engine.state.set('health', health);
  engine.state.set('fuel', fuel);
[continued]
{embed passage: "CheckStatus"}

:: GREEN
REPORT
[JavaScript]
  let percentage = Math.randomRange(0, 11);
  let foundFuel = 0;
  let foundHealth = 0;
  let fuel = engine.state.get('fuel');
  let health = engine.state.get('health');
  
  
  if(percentage < 2) {
  
    foundFuel = Math.randomRange(1,3);
    write(`Fuel was found in some wreckage. (+${foundFuel} to fuel)`);
    fuel += foundFuel;
  
  }
  
  if(percentage > 6) {
  
    foundHealth = Math.randomRange(1,4);
    write(`During a brief pause, the ship was able to be repaired. (+${foundHealth} to health)`);
    health += foundHealth;
  
  }
  
  if(percentage > 2 && percentage < 6)
  {
    write(`Nothing happened.`);
  }

  engine.state.set('health', health);
  engine.state.set('fuel', fuel);
[continued]
{embed passage: "CheckStatus"}

:: Statistics
Health: {health}

Fuel: {fuel}

Number of Jumps Left: {numberOfJumpsLeft}

{reveal link: 'Statistics', passage: 'Statistics'}

```

[Twee Download](chapbook_space_exploration_twee.txt){ target="_top" download="chapbook_space_exploration_twee.txt"}
