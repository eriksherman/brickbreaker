# BrickBreaker (HTML Canvas Demo)

Summary: A concise, dependency-free Brick Breaker game built with HTML5 Canvas. It runs entirely in the browser with a simple game loop, a paddle, a ball, and bricks. This single-file demo is ideal for learning Canvas rendering and basic game mechanics.

A tiny single-file brick breaker game implemented in plain HTML5 Canvas and JavaScript. No libraries required.

## Overview
- Runs entirely client-side in the browser.
- Uses a canvas-based rendering loop to draw a ball, paddle, and bricks.
- Ball bounces off walls, bricks, and the paddle. Missing the paddle ends the game; destroying all bricks wins the round.

## How to Run
- Open `index.html` directly in a modern browser.
- Optional: serve the repo with a simple HTTP server, for example:
  - Python 3: `python -m http.server 8000` and open `http://localhost:8000/`.
- No build step required; changes can be edited in-place and refreshed in the browser.

## Game Architecture
- `index.html` contains the entire game: canvas setup, game loop, rendering, and logic.
- Core elements:
  - Ball: position (`x`, `y`), velocity (`dx`, `dy`), radius, color.
  - Paddle: position (`paddleX`), size (`paddleWidth`, `paddleHeight`).
  - Bricks: grid generated from `brickRowCount`, `brickColumnCount`, `brickWidth`, `brickHeight`, `brickPadding`, `brickOffsetLeft`, `brickOffsetTop`.
- Collision handling:
  - Ball-wall collisions invert velocity.
  - Ball-brick collisions set brick to invisible/destroyed and invert ball direction.
  - Ball-paddle collision bounces the ball upward.

## How It Works (Brief Walkthrough)
- The `draw()` loop clears the canvas, renders bricks, ball, paddle, and score, then updates positions and checks collisions.
- Keyboard input is handled via `keydown`/`keyup` events to move the paddle left/right.
- Score increases when bricks are destroyed; game ends on miss or fills all bricks.

## Customization
- Adjust gameplay by editing constants in `index.html`:
  - Ball: `dx`, `dy`, `ballRadius`, `ballColor`.
  - Paddle: `paddleWidth`, `paddleHeight`.
  - Bricks: `brickRowCount`, `brickColumnCount`, `brickWidth`, `brickHeight`, `brickPadding`, `brickColor`.
- Add more levels or features by introducing new logic in the same file.

## File Overview
- `index.html` — single-file game containing the canvas and all JS logic.
- No external assets or dependencies.

## Extending (Ideas)
- Add touch or mouse controls for mobile.
- Implement a pause/restart feature.
- Persist high scores to `localStorage` and display them.

## License
This project uses the default repository license and is intended for educational/demo use.
