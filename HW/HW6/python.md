```python
from typing import List

class main:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        nums.sort()
        result = []

        if len(nums) < 3 or nums[0] > 0:
            return result

        num_map = {}
        for i, num in enumerate(nums):
            num_map[num] = i

        prev_triplet = None
        for i in range(len(nums) - 2):
            if nums[i] > 0:
                break
            if i > 0 and nums[i] == nums[i-1]:
                continue

            for j in range(i + 1, len(nums) - 1):
                complement = -1 * (nums[i] + nums[j])
                if complement in num_map and num_map[complement] > j:
                    triplet = [nums[i], nums[j], complement]
                    if triplet != prev_triplet:
                        result.append(triplet)
                        prev_triplet = triplet
                j = num_map[nums[j]]

            i = num_map[nums[i]]

        return result

# Test
arr = [-5, 0, 5, 10, -10, 0]
solution = main()
print(solution.threeSum(arr))

