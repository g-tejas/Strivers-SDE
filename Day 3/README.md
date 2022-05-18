# Search A 2D Matrix

```python

rowIndex = 0
for row in matrix:
    if target <= row[-1]:
        break
    rowIndex += 1
try:
    for i in matrix[rowIndex][::-1]:
        if target == i:
            return True
    return False
except: return False

```

# Power Function

```python

def myPow(self, x, n):
    if not n:
        return 1
    if n < 0:
        return 1 / self.myPow(x, -n)
    if n % 2:
        return x * self.myPow(x, n-1)
    return self.myPow(x*x, n/2)

```

# Majority Element In Array

```python

return sorted(nums)[len(nums)/2]

```

# Majority 1/3 Element In Array

```python

num1 = 0
num2 = 0
c1 = 0
c2 = 0
for i in nums:
    if num1 == i:
        c1 += 1
    elif num2 == i:
        c2 += 1
    elif c1 == 0:
        c1 = 1
        num1 = i
    elif c2 == 0:
        c2 = 1
        num2 = i
    else:
        c2 -= 1
        c1 -= 1
num1sum = [1 for i in nums if num1 == i]
num2sum = [1 for i in nums if num2 == i]
answer = []
if len(num1sum) > len(nums)/3:
    answer.append(num1)
if len(num2sum) > len(nums)/3:
    answer.append(num2)
return list(set(answer))

```

# Grid Unique Paths

```python

if m < n:
    temp = m
    m = n
    n = temp
res = 1
for i in range(1, m):
res = res * (n-1+i) / i
return int(res)

```

# Count Reverse Pairs

```python

if len(nums) <= 1:
    return 0
count = [0]

def merge(nums):
    if len(nums) <= 1: return nums

    left, right = merge(nums[:len(nums)//2]), merge(nums[len(nums)//2:])
    l = r = 0

    while l < len(left) and r < len(right):
        if left[l] <= 2 * right[r]:
            l += 1
        else:
            count[0] += len(left) - l
            r += 1
    return sorted(left+right)

merge(nums)
return count[0]

```


