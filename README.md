# Super Darts

This game is an implementation of the game Darts. The game has no sprites at all and every line is drawn on the fly.

[PLAY DEMO](https://robsonbotelho.github.io/play-darts/)

## About This game

Super Darts is a simple implementation of the game Darts and everything you see is drawn using only HTML5 Canvas (no image sprites were used).

The gameplay controls are similar to the ones from Grand Theft Auto darts game which consists of a shaking aim that can be controled by the user in order to throw the darts.

You can play with another person on the same computer. No AI or remote multiplayer is implemented (and there are no plans of doing so).

## How to Play

Download the project and open `index.html` in your browser.
When asked, fill in you name and your partner's name (player 1 and player 2 respectively).
To control the aim, use the **arrow keys** on your keyboard and to throw the dart hit **space bar**. To pause hit **ESC**.

Each player starts with 301 points and the first one to reach 0 wins. Your last shot must be wither bulls-eye (50 points) or a double (outer ring).
The official rules can be [found here](http://www.ndadarts.com/rules/rules-play-301501).


## How it Works

The game runs on HTML5's Canvas and its logic is written using pure Javascript.
The main file `game.js` is divided by the following sections:

### GAME SETUP
Contains game configuration settings such as the canvas selector and its context and stage setup including its viewport size (width and height) as well as its center point (used for reference as a starting point when drawing on the canvas).

### UTILITIES
A set of useful functions stored in the variable `utils`. Currently there are only 2 functions: `toDegrees()` which converts radians values to degrees and `numberInRange()` which has the simple task to return true if a given number is in the range of other two numbers. Some other methods could be added our utils on a later update.

The Utilities section also contains the `color` variable and the `input` variable (which stores the current position of the aim).

### RENDERING
The rendering functions responsible for drawing each of the game elements on the canvas (board, aim, dart, message and HUD) (For more details on how each of these methods works please see the source code which is well commented).

### INPUT HANDLING
Set of methods used to handle input from the user. Currently only two of those methods are used: `OnKeyDown()` which handles keyboard input from the player in order to move the aim and throw the dart and `OnMouseMove()` which is used to just move the aim freely without any difficulty (currently used only for debugging).

### GAMEPLAY
The variable `players` stores each of the users information such as name, color and score. The variable `game` stores all the game related settings such as timeScale, game pause, board scores and the player's turn info (For more information please see the comments in the source code).

### EVENTS
Currently, the only event that is dispatched is the `throwDart`. All of the game logic for this event is stored within the homonymous function.

### GAME METHODS
Similar to some game engines structure. See below:
- `awake()` - is called once before the game starts;
- `start()` - is called once to initialize the game;
- `update()` - also known as "frame update", this method is called once on each frame. The game is suposed to run on a 60FPS basis so we set this method to be called once every 16.67 miliseconds (divided by the previously set `timeScale` value in order to keep the pace of the game).

## Report Issues
This is a personal project but suggestions are welcome. There are a couple of known bugs which are foreseen to be fixed in the next update coming soon.