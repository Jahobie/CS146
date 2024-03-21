# Flood Fill Algorithm

## Problem Description
Given an image represented by a 2D array of integers, an initial pixel position `(sr, sc)`, and a new color value, perform a flood fill on the image starting from the initial position. The flood fill replaces the color of the initial position and all of its adjacent positions with the new color, as long as they have the same original color as the initial position.

## Approach
The problem can be solved using a Depth-First Search (DFS) approach. Here's the outline of the approach:

1. Define a helper function `bfs` that performs a depth-first search on the image.
2. In the `bfs` function:
   - Check if the current position is within the boundaries of the image, if it's already visited, or if its color is not the same as the original color. If any of these conditions are true, return.
   - Update the color of the current position to the new color and mark it as visited.
   - Recursively call the `bfs` function for all four adjacent positions (up, down, left, right).
3. In the main `floodFill` function:
   - Create a boolean matrix to keep track of visited positions.
   - Get the original color of the initial position.
   - Call the `bfs` function starting from the initial position.


