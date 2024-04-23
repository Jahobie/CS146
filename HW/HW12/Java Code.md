``` Java
import java.util.*;

public class Solution {
    public int minCostToSupplyWater(int n, int[] wells, int[][] pipes) {
        // Create a priority queue to store edges sorted by their costs
        PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> a[2] - b[2]);
        
        // Add all wells as edges to the priority queue
        for (int i = 0; i < wells.length; i++) {
            pq.offer(new int[]{0, i + 1, wells[i]}); // Adding 0 as a virtual node to represent well at each house
        }
        
        // Add all pipes as edges to the priority queue
        for (int[] pipe : pipes) {
            pq.offer(pipe);
        }
        
     
        Set<Integer> visited = new HashSet<>();
        
        int totalCost = 0;
        // Initialize with the first house
        visited.add(0);
        
    
        while (visited.size() < n + 1) { // Additional 1 for the virtual node 0
            int[] edge = pq.poll();
            int house1 = edge[0];
            int house2 = edge[1];
            int cost = edge[2];
            
            // If both houses are not visited yet, add the cost and mark them as visited
            if (visited.contains(house1) && !visited.contains(house2) ||
                visited.contains(house2) && !visited.contains(house1)) {
                totalCost += cost;
                visited.add(visited.contains(house1) ? house2 : house1);
            }
        }
        
        return totalCost;
    }
}
``` 
