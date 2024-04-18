```Python
import heapq

class Solution:
    def findTheCity(self, n: int, edges: List[List[int]], distanceThreshold: int) -> int:
        # Create adjacency list to represent the graph
        graph = {i: [] for i in range(n)}
        for edge in edges:
            from_city, to_city, weight = edge
            graph[from_city].append((to_city, weight))
            graph[to_city].append((from_city, weight))
        
        min_cities = float('inf')
        result = -1
        
        # Iterate over each city and apply Dijkstra's algorithm
        for i in range(n):
            pq = [(0, i)]  # Start from current city with distance 0
            visited = set()
            reachable_cities = 0
            
            while pq:
                dist, city = heapq.heappop(pq)
                
                if city in visited:
                    continue
                
                visited.add(city)
                
           
                if dist > distanceThreshold:
                    break
                
             
                reachable_cities += 1
                
           
                for neighbor, weight in graph[city]:
                    if neighbor not in visited:
                        heapq.heappush(pq, (dist + weight, neighbor))
           
            if reachable_cities <= min_cities:
                min_cities = reachable_cities
                result = i
        
        return result
```
