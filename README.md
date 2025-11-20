# Maze Generator and Solver
This project explores various techniques to both generate and solve mazes by implementing them in Python. This is all visualised with a full real time display in PyGame. When you start the program with the selected options, a maze is created cell by cell and then the solver takes over and searches for a path through that maze. The maze itself is stored as a grid in memory and displayed using coloured cells, each colour representing a different state.

## Maze Generation
The generator builds the maze by walking through the grid one cell at a time until it has filled in the entire grid. It uses a queue to store cells it still needs to visit. Two settings control how this works.

Queue method controls the order news cells are taken from the queue:
- LIFO (last in first out) works like a stack and creates long corridors.
- FIFO (first in first out) works like a normal queue and spreads out more evenly.

Choose method controls how the generator picks the next unvisited neighbour:
- Random picks a neighbour at random, leading to a natural and twisty maze.
- First always picks the first neighbour in the list.
- Last always picks the last neighbour in the list.

Using LIFO with random gives the normal recursive backtracker.

## Maze Solving
The solver tries to reach the end cell (bottom right) from the start cell (top left). Every time it tries a new move, it marks the cell as queued. When the solver pops a path from the queue, it marks the cell as searched.

Algorithm controls which path the solver will follow:
- bfs (breadth first search) checks paths in rings spreading out from the start. It always finds the shortest path.
- dfs (depth first search) dives down one path until it cannot continue, then backtracks. It does not guarantee the shortest path.

The solver ends when it reaches the end cell. It then walks back through the path and marks it so you can see the full path through the maze.

## Demo
![Demo](demo/demo.gif)
