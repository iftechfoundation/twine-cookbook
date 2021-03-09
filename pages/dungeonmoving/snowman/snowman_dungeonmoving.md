# "Moving through a 'dungeon": Snowman (1.3.0)

## Summary

"Moving through a 'dungeon'" creates a multidimensional array. Movement positions are then tracked through X and Y variables for a grid system. Each movement subtracts or adds to its corresponding X or Y position and is compared to those same positions within the array. Different directions are shown if movement is possible in that direction.

## Example

[Download](snowman_dungeonmoving_example.html){: target="_top" download="snowman_dungeonmoving_example.html"}

## Twee Code

```twee
:: Start
<div class="maze"></div>

<button type="button" data-move="n">North</button>
<button type="button" data-move="s">South</button>
<button type="button" data-move="e">East</button>
<button type="button" data-move="w">West</button>

<%
/* 0s are walls, 1 are spaces, 2 is the goal. */
var maze =
[
[0,0,0,0,0,0,0,0,0,0,0],
[0,1,1,1,0,1,1,1,1,1,0],
[0,0,0,1,0,0,0,0,0,1,0],
[0,1,0,1,1,1,1,1,0,1,0],
[0,1,0,0,0,0,0,1,0,1,0],
[0,1,1,1,1,1,1,1,0,1,0],
[0,0,0,0,0,0,0,1,0,1,0],
[0,1,0,1,1,1,1,1,1,1,0],
[0,1,0,1,0,0,0,1,0,0,0],
[0,1,1,1,0,1,1,1,1,2,0],
[0,0,0,0,0,0,0,0,0,0,0]
];

/* Where the player starts. The top left is (0, 0). */

var positionX = 1, positionY = 1;

function renderMaze() {
  /* Transform the maze into ASCII art. */
  
  /* What characters we use to display the maze. */
  var displayChars = ['#', '.', 'E'];

  $('.maze').html(maze.map(function(row, renderY) {
    return row.reduceRight(function(html, cell, renderX) {
      if (renderX === positionX && renderY === positionY) {
        return 'P' + html;
      }
  
      return displayChars[cell] + html;
    }, '<br>');
  }));
}

function updateMoves() {
  /*
  Enable/disable buttons to move based on what's allowed.
  We take advantage of the fact that both 0 and undefined
  (outside the maze) are converted to false by JavaScript by the
  ! operator.
  */

  $('[data-move="n"]').attr('disabled', !maze[positionY - 1][positionX]);
  $('[data-move="s"]').attr('disabled', !maze[positionY + 1][positionX]);
  $('[data-move="e"]').attr('disabled', !maze[positionY][positionX + 1]);
  $('[data-move="w"]').attr('disabled', !maze[positionY][positionX - 1]);
}

$(function() {
  renderMaze();
  updateMoves();
  
  /*
  Change position when the user clicks an appropriate link.
  We depend on updateMoves() to prevent the user from walking
  through a wall.
  */

  $('[data-move]').click(function() {
    var direction = $(this).data('move');
  
    switch (direction) {
      case 'n':
        positionY--;
        break;
      case 's':
        positionY++;
        break;
      case 'e':
        positionX++;
        break;
      case 'w':
        positionX--;
        break;
      default:
        throw new Error('Don\'t know how to move ' + direction);
    }
  
    if (maze[positionY][positionX] === 2) {
      story.show('Exit');
    }
    else {
      renderMaze();
      updateMoves();
    }
  });
});

%>


:: Exit
You've escaped this fiendish maze!
```

[Twee Download](snowman_dungeonmoving_twee.txt){ target="_top" download="snowman_dungeonmoving_twee.txt"}

[Setting and Showing Variables](../../settingandshowing/snowman/snowman_settingandshowing.md),
[Conditional Statements](../../conditionalstatements/snowman/snowman_conditionalstatements.md)
