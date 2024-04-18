# Finding the City with the Smallest Number of Reachable Cities

## Problem Statement

Given a graph representing cities and bidirectional weighted edges between them, along with a distance threshold, the task is to find the city with the smallest number of cities that are reachable through some path and whose distance is at most the distance threshold. If there are multiple such cities, return the city with the greatest number.

## Approach

To solve this problem, we can use Dijkstra's algorithm to find the shortest paths from each city to all other cities. Then, for each city, we can count how many cities are reachable within the given distance threshold.

