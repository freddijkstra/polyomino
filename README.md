# Polyomino Packing Problem Solver

## Overview
This program aims to solve a polyomino packing problem, where the goal is to place a set of predefined shapes onto a matrix without any overlaps or shapes going outside the matrix boundaries. The shapes can be rotated as needed. The solution provides the locations and number of clockwise rotations for each shape.

## Design

### Data Structures

1. **Shapes**: Represented as a list of tuples. Each tuple contains the (row, column) coordinate of a block in the shape relative to the top-left block.

```python
blue    = [(0, 0), (1, 0), (1, 1)]
green   = ...
...
shapes = [blue, green, ...]
```

2. **Matrix**: A 2D list of integers where each block is represented by an integer. Initially, all blocks are set to 0. When a shape is placed, the corresponding blocks are incremented.

### Core Functions

1. ``rotate_shape()``: Rotates a given shape 90 degrees clockwise.

2. ``generate_empty_matrix()``: Generates an empty matrix of the given dimensions.

3. ``place_shape()``: Attempts to place a shape onto the matrix at a given location. Returns `None` if the shape can't be placed.

4. ``remove_shape()``: Removes a shape from the matrix.

5. ``solve()``: The main function that recursively attempts to place each shape onto the matrix, backtracking as necessary.

## Implementation

The primary approach is a depth-first search algorithm. For each shape:

1. Rotate the shape (0 to 3 times) and try to fit it in the current matrix.
2. If the shape fits, proceed with the next shape.
3. If the shape doesn't fit in any rotation, backtrack to the previous shape and continue searching.

The search stops when all shapes are successfully placed or all possibilities are exhausted.

## Usage

1. Define your shapes and initialize the matrix.
2. Call the `solve()` function.
3. If a solution is found, it will be printed with the shape's position and number of rotations.
