import java.util.*;

public class Solution {
    public List<List<Integer>> getSkyline(int[][] buildings) {
        List<List<Integer>> result = new ArrayList<>();
        List<int[]> events = new ArrayList<>();
        for (int[] building : buildings) {
            events.add(new int[]{building[0], building[2], 1});  
            events.add(new int[]{building[1], building[2], -1}); 
        }
        
        // Step 2: Sort the events
        Collections.sort(events, (a, b) -> {
            if (a[0] != b[0]) return a[0] - b[0];
            if (a[2] != b[2]) return b[2] - a[2];
            return a[2] == 1 ? b[1] - a[1] : a[1] - b[1];
        });
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
        maxHeap.add(0);  
        int prevMaxHeight = 0;
        for (int[] event : events) {
            int x = event[0];
            int height = event[1];
            int type = event[2];
            
            if (type == 1) {
                maxHeap.add(height);
            } else {
                maxHeap.remove(height);
            }
            int currentMaxHeight = maxHeap.peek();
            if (currentMaxHeight != prevMaxHeight) {
                result.add(Arrays.asList(x, currentMaxHeight));
                prevMaxHeight = currentMaxHeight;
            }
        }
        
        return result;
    }
}
