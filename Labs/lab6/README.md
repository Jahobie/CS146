# Course Schedule

## Problem Description

You are given a total of `numCourses` courses you have to take, labeled from 0 to `numCourses - 1`. You are also given an array `prerequisites` where `prerequisites[i] = [ai, bi]` indicates that you must take course `bi` first if you want to take course `ai`.

For example, the pair `[0, 1]` indicates that to take course 0 you have to first take course 1.

Return `true` if you can finish all courses. Otherwise, return `false`.


## Approach Explanation

To solve this problem, we can use a graph-based approach. We represent the courses and their prerequisites as a directed graph, where each course is a node and each prerequisite relationship is a directed edge from one course to another. Then, we perform a topological sort on this graph to determine if it's possible to complete all courses.

The steps of the approach are as follows:

1. **Create an Adjacency List**: We create an adjacency list representation of the graph where each node represents a course and its prerequisites are represented as edges.

2. **Depth-First Search (DFS)**: We perform a depth-first search (DFS) on each node of the graph. During the DFS traversal, we keep track of nodes that are currently being visited (`inProcess`). If we encounter a node that is already in the `inProcess` array, it means we have found a cycle in the graph, indicating that it's not possible to complete all courses. If no cycle is detected, we mark the node as visited and proceed with DFS traversal.

3. **Check for Cycle**: After DFS 
