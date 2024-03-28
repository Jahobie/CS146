```Python
from collections import defaultdict

class Solution:
    def canFinish(self, numCourses: int, prerequisites: List[List[int]]) -> bool:
        # Create adjacency list representation of the graph
        adj_list = defaultdict(list)
        for course, prereq in prerequisites:
            adj_list[prereq].append(course)
        
        # Array to keep track of visited nodes during DFS
        visited = [False] * numCourses
        
        # Array to keep track of nodes currently being visited during DFS
        in_process = [False] * numCourses
        
        # DFS function to detect cycles
        def has_cycle(node):
            if in_process[node]:
                return True  # Cycle detected
            
            if visited[node]:
                return False  # Already visited, no cycle
            
            visited[node] = True
            in_process[node] = True
            
            for neighbor in adj_list[node]:
                if has_cycle(neighbor):
                    return True  # Cycle detected in neighbor
            
            in_process[node] = False
            
            return False
        
        # Perform DFS on each node
        for i in range(numCourses):
            if not visited[i] and has_cycle(i):
                return False  # Cycle detected, can't finish all courses
        
        return True  # No cycle detected, can finish all courses
```
