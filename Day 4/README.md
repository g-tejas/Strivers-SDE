# 2 Sum Problem

```python

seen = {}
for i in range(len(nums)):
    if (target-nums[i]) in seen:
        return [i, seen[target-nums[i]]]
    seen[nums[i]] = i

```

# Four Sum Problem (k-Sum Generalisation)

```python

class Solution:
    def fourSum(self, nums: List[int], target: int) -> List[List[int]]:
	
        def kSum(nums: List[int], target: int, k: int) -> List[List[int]]:
            res = []
            
            # If we have run out of numbers to add, return res.
            if not nums:
                return res
            
            # There are k remaining values to add to the sum. The 
            # average of these values is at least target // k.
            average_value = target // k
            
            # We cannot obtain a sum of target if the smallest value
            # in nums is greater than target // k or if the largest 
            # value in nums is smaller than target // k.
            if average_value < nums[0] or nums[-1] < average_value:
                return res
            
            if k == 2:
                return twoSum(nums, target)
    
            for i in range(len(nums)):
                if i == 0 or nums[i - 1] != nums[i]:
                    for subset in kSum(nums[i + 1:], target - nums[i], k - 1):
                        res.append([nums[i]] + subset)
    
            return res

        def twoSum(nums: List[int], target: int) -> List[List[int]]:
            res = []
            lo, hi = 0, len(nums) - 1
    
            while (lo < hi):
                curr_sum = nums[lo] + nums[hi]
                if curr_sum < target or (lo > 0 and nums[lo] == nums[lo - 1]):
                    lo += 1
                elif curr_sum > target or (hi < len(nums) - 1 and nums[hi] == nums[hi + 1]):
                    hi -= 1
                else:
                    res.append([nums[lo], nums[hi]])
                    lo += 1
                    hi -= 1
                                                         
            return res

        nums.sort()
        return kSum(nums, target, 4)
```

# Longest Consecutive Sequence

```python        

longest_streak = 0
num_set = set(nums)
for num in num_set:
    if num-1 not in num_set:
        current_num = num
        current_streak = 1
        while current_num+1 in num_set:
            current_streak += 1
            current_num += 1
        longest_streak = max(current_streak, longest_streak)
return longest_streak

```

# Longest Subarray Zero Sum

```python

mpp = {}
maxi = 0
sum = 0
for i, value in enumerate(arr):
    sum += value
    if sum == 0:
        maxi = i + 1
    else:
        if sum in mpp:
            maxi = max(maxi, i - mpp[sum])
        else:
            mpp[sum] = i
return maxi

```

# Longest Substring Without Repeating Characters 

```python

currentSubstring = ''
maxi = 0
for i in s:
    if i not in currentSubstring:
        currentSubstring += i
    else:
        maxi = max(maxi, len(currentSubstring))
        currentSubstring += i
        currentSubstring = currentSubstring[currentSubstring.index(i)+1:]
return max(maxi, len(currentSubstring))

```


