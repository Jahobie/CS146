```Python
import heapq

class Solution:
    def minCostToSupplyWater(self, n: int, wells: List[int], pipes: List[List[int]]) -> int:
  
        pq = []
        

        for i in range(len(wells)):
            heapq.heappush(pq, (wells[i], 0, i + 1)) 
        
        for pipe in pipes:
            heapq.heappush(pq, (pipe[2], pipe[0], pipe[1]))
        
  
        visited = set()
        
        total_cost = 0

        visited.add(0)
        
     
        while len(visited) < n + 1: # Additional 1 for the virtual node 0
            cost, house1, house2 = heapq.heappop(pq)
            
         
            if (house1 in visited and house2 not in visited) or (house2 in visited and house1 not in visited):
                total_cost += cost
                visited.add(house1 if house2 in visited else house2)
        
        return total_cost
```
