# Rotate Matrix

```python
n = len(matrix[0])
for i in range(n // 2 + n % 2):
    for j in range(n // 2):
        tmp = matrix[n - 1 - j][i]
        matrix[n - 1 - j][i] = matrix[n - 1 - i][n - j - 1]
        matrix[n - 1 - i][n - j - 1] = matrix[j][n - 1 -i]
        matrix[j][n - 1 - i] = matrix[i][j]
        matrix[i][j] = tmp
```

# Merge Overlapping Subintervals

```python
intervals = sorted (intervals)
answer = [intervals[0]]
for i, value in enumerate (intervals):
	if value[0] > answer[-1][1]:
		answer.append (value)
	else:
		answer[-1] = [answer[-1][0], max(answer[-1][1], value[1])]

```

# Merge Two Sorted Arrays Without Extra Space

```python
while n:
    if m and nums1[m - 1] >= nums2[n - 1]:
        nums1[m + n - 1] = nums1[m - 1]
        m -= 1
    else:
        nums1[m + n - 1] = nums2[n - 1]
        n -= 1

```

# Find The Duplicate In An Array with N+1 Integers

```python
slow = nums[0]
fast = nums[0]
while True:
    slow = nums[slow]
    fast = nums[nums[fast]]
    if slow == fast:
        break
fast = nums[0]
while slow != fast:
    slow = nums[slow]
    fast = nums[fast]

```
