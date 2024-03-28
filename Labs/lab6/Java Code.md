```Java
import java.util.*;

public class CourseSchedule {
    public boolean canFinish(int numCourses, int[][] prerequisites) {
        // Create an adjacency list representation of the graph
        List<List<Integer>> adjList = new ArrayList<>();
        for (int i = 0; i < numCourses; i++) {
            adjList.add(new ArrayList<>());
        }
        
        // Populate the adjacency list
        for (int[] prerequisite : prerequisites) {
            adjList.get(prerequisite[1]).add(prerequisite[0]);
        }
        
        // Array to keep track of visited nodes during DFS
        boolean[] visited = new boolean[numCourses];
        
        // Array to keep track of nodes currently being visited during DFS
        boolean[] inProcess = new boolean[numCourses];
        
        // Perform DFS on each node
        for (int i = 0; i < numCourses; i++) {
            if (!visited[i] && hasCycle(i, adjList, visited, inProcess)) {
                return false; // Cycle detected, can't finish all courses
            }
        }
        
        return true; // No cycle detected, can finish all courses
    }
    
    private boolean hasCycle(int node, List<List<Integer>> adjList, boolean[] visited, boolean[] inProcess) {
        if (inProcess[node]) {
            return true; // Cycle detected
        }
        
        if (visited[node]) {
            return false; // Already visited, no cycle
        }
        
        visited[node] = true;
        inProcess[node] = true;
        
        for (int neighbor : adjList.get(node)) {
            if (hasCycle(neighbor, adjList, visited, inProcess)) {
                return true; // Cycle detected in neighbor
            }
        }
     
```
