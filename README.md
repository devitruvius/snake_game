# Snake Game with Pygame

## Description

This Python code implements a classic Snake Game using the Pygame library. Players control a snake that grows longer by eating food and avoid hitting the walls or itself.

## Installation

1. Install Pygame
   
    ```python
    # Bash
    
    pip install pygame
    ```

## Running the Game

1. Save the code as <code>snake_game.py</code>
2. Run the script from your terminal:

    ```python
    # Bash
  
    python snake_game.py
    ```

## Gameplay

* Use the arrow keys (W, A, S, D) to control the snake's direction.
* The snake grows longer by eating the red food squares.
* Avoid hitting the walls (borders of the screen) or the snake's own body.
* The game restarts if the snake collides with anything.

## Code Breakdown

1. Imports:
   * <code>pygame</code>: Used for creating the game window, handling events, and drawing graphics.
   * <code>random</code>: Used for generating random positions for the food.
  
2. Configuration:
   * <code>WINDOW</code>: Width and height of the game window in pixels (default 700x700).
   * <code>TILE_SIZE</code>: Size of each snake segment and food square in pixels (default 50).
   * <code>RANGE</code>: Used to generate random positions within the game window.
   * <code>get_random_position</code>: Function that generates a random position within the allowed range.
   * <code>snake</code>: Initial snake position and size as a <code>pygame.Rect</code> object.
   * <code>length</code>: Current length of the snake (starts at 1).
   * <code>segments</code>: List of <code>pygame.Rect</code> objects representing the snake's body segments.
   * <code>snake_dir</code>: Direction of the snake's movement (initially stopped).
   * <code>time, time_step</code>: Variables used to control the game's speed.
   * <code>food</code>: Position and size of the food as a <code>pygame.Rect</code> object.
   * <code>screen</code>: Surface object representing the game window created using <code>pygame.display.set_mode</code>.
   * <code>clock</code>: Clock object used to control the game's frame rate.
   * <code>dirs</code>: Dictionary that maps arrow keys to movement directions (used to prevent immediate reversal).
  
3. Main Loop:
   * The game loop runs continuously until the player quits.
   * Event Handling:
     * Checks for events like key presses and quitting the game.
     * Updates the <code>snake_dir</code> variable based on the pressed arrow key, preventing immediate reversal using the <code>dirs</code> dictionary.
   * Drawing:
     * Fills the screen with black background color.
   * Collision Detection & Game Over:
     * Checks if the snake collides with the walls or itself. If so, resets the snake's position and length.
   * Food Consumption & Growth:
     * Checks if the snake eats the food. If so, generates a new food position and increases the snake's length.
   * Drawing Food:
     * Draws a red rectangle for the food.
   * Drawing Snake:
     * Draws white rectangles for each segment of the snake's body.
   * Movement:
     * Updates the snake's position based on the current direction and time elapsed.
     * Updates the <code>segments</code> list by adding a new segment at the head and removing the oldest one (maintains snake length).
     * Limits the number of segments in the <code>segments</code> list to the snake's current length.
   * Display Update:
     * Updates the game window with all the drawn elements.
   * Frame Rate Control:
     * Limits the game's frame rate to 60 frames per second for smoother movement.

## Additional Notes:

* You can adjust the <code>WINDOW</code> and <code>TILE_SIZE</code> variables to customize the game's appearance.
* Experiment with the <code>time_step</code> variable to change the speed of the game.
* Consider adding features like score tracking and increasing difficulty levels.
* Feel free to modify the code to create your own variations of the Snake Game!
