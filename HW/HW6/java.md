
```java
import java.util.*;

public class Main {

    public static List<List<Integer>> threeSum(int[] nums) {
        Arrays.sort(nums);
        List<List<Integer>> result = new ArrayList<>();

        if (nums.length < 3 || nums[0] > 0)
            return result;

        Map<Integer, Integer> numMap = new HashMap<>();
        for (int i = 0; i < nums.length; i++)
            numMap.put(nums[i], i);

        for (int i = 0; i < nums.length - 2; i++) {
            if (nums[i] > 0)
                break;

            for (int j = i + 1; j < nums.length - 1; j++) {
                int complement = -1 * (nums[i] + nums[j]);
                if (numMap.containsKey(complement) && numMap.get(complement) > j) {
                    result.add(Arrays.asList(nums[i], nums[j], complement));
                }
                j = numMap.get(nums[j]);
            }

            i = numMap.get(nums[i]);
        }

        return result;
    }

    public static void main(String[] args) {
        int[] arr = new int[]{-5, 0, 5, 10, -10, 0};
        System.out.println(threeSum(arr));
    }
}

