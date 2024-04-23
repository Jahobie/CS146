# Minimum Cost to Supply Water - Graph Problem

## Problem Statement

There are `n` houses in a village. We want to supply water for all the houses by building wells and laying pipes.

For each house `i`, we can either build a well inside it directly with cost `wells[i - 1]` (note the -1 due to 0-indexing), or pipe in water from another well to it. The costs to lay pipes between houses are given by the array `pipes` where each `pipes[j] = [house1j, house2j, costj]` represents the cost to connect `house1j` and `house2j` together using a pipe. Connections are bidirectional, and there could be multiple valid connections between the same two houses with different costs.

The task is to return the minimum total cost to supply water to all houses.



## Approach  Prim's Algorithm with Priority Queue



- Create a priority queue to store edges sorted by their costs.
- Add all wells as edges to the priority queue.
- Add all pipes as edges to the priority queue.
- Use Prim's algorithm to find the minimum spanning tree of the graph formed by houses and pipes.
- Maintain a set to keep track of visited houses.

