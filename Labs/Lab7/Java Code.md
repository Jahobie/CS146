```Java
import java.util.*;

public class Solution {
    public int findTheCity(int n, int[][] edges, int distanceThreshold) {
        // Create adjacency list to represent the graph
        Map<Integer, List<int[]>> graph = new HashMap<>();
        for (int i = 0; i < n; i++) {
            graph.put(i, new ArrayList<>());
        }
        for (int[] edge : edges) {
            int from = edge[0];
            int to = edge[1];
            int weight = edge[2];
            graph.get(from).add(new int[]{to, weight});
            graph.get(to).add(new int[]{from, weight});
        }
        
        int minCities = Integer.MAX_VALUE;
        int result = -1;
        
        // Iterate over each city and apply Dijkstra's algorithm
        for (int i = 0; i < n; i++) {
            PriorityQueue<int[]> pq = new PriorityQueue<>(Comparator.comparingInt(a -> a[1]));
            pq.offer(new int[]{i, 0}); // Start from current city with distance 0
            Set<Integer> visited = new HashSet<>();
            int reachableCities = 0;
            
            while (!pq.isEmpty()) {
                int[] curr = pq.poll();
                int city = curr[0];
                int dist = curr[1];
                
                if (visited.contains(city)) continue;
                visited.add(city);
                
              
                if (dist > distanceThreshold) break;
                
               
                reachableCities++;
                
                
                for (int[] neighbor : graph.get(city)) {
                    int nextCity = neighbor[0];
                    int weight = neighbor[1];
                    if (!visited.contains(nextCity)) {
                        pq.offer(new int[]{nextCity, dist + weight});
                    }
                }
            }
            
            
            if (reachableCities <= minCities) {
                minCities = reachableCities;
                result = i;
            }
        }
        
        return result;
    }
}

```
