# Fill Matrix Zeroes

```python
col0 = 1
rows = len(matrix)
cols = len(matrix[0])
for i in range(rows):
    if matrix[i][0] == 0:
        col0 = 0
    for j in range(1, cols):
        if matrix[i][j] == 0:
            matrix[i][0] = 0
            matrix[0][j] = 0  

for i in range(rows-1, -1, -1):
for j in range(cols-1, 0, -1):
    if matrix[i][0] == 0 or matrix[0][j] == 0:
        matrix[i][j] = 0
if col0 == 0:
    matrix[i][0] = 0
```

# Pascal’s Triangle

```python
answer = [[1]]

for i in range(1, numRows):
    if i == 1:
        answer.append([1,1])
    else:
        newList = [1]
        for j in range(1, i):
            newList.append(answer[i-1][j-1] + answer[i-1][j])
        newList.append(1)
        answer.append(newList)
```

# Next Permutation

```python
if nums == sorted(nums)[::-1]:
    for i in range(len(nums)/2):
        temp = nums[i]
        nums[i] = nums[(len(nums))-1-i]
        nums[(len(nums))-1-i] = temp
    return

prev = nums[-1]
index2 = 0
index1 = 0
for i in range(len(nums)-2, -1, -1):
    print(i)
    if nums[i] < prev:
        index2 = i
        break
    prev = nums[i]

for i in range(len(nums)-1, index2, -1):
    if nums[i] > nums[index2]:
        index1 = i
        break
temp = nums[index2]
nums[index2] = nums[index1]
nums[index1] = temp

nums[index2+1:] = reversed(nums[index2+1:])
```

# Kadane’s Algorithm

```python
local = 0
globalnum = 0
for i,value in enumerate(nums):
    local = max(value, local+value)
    globalnum = max(globalnum, local) if i!=0 else local
return globalnum
```

# Sort Colours

```python
low = 0
mid = 0
high = len(nums)-1
while mid <= high:
    if nums[mid] == 0:
        nums[mid] = nums[low]
        nums[low] = 0
        low+=1
        mid+=1
    elif nums[mid] == 1:
        mid+=1
    else:
        nums[mid] = nums[high]
        nums[high] = 2
        high-=1
```

# Best Time To Buy And Sell Stock

```python
cheapestBuy = prices[0]
bestSell = 0
for i, value in enumerate(prices[1:]):
    bestSell = bestSell if (value - cheapestBuy) < bestSell else (value - cheapestBuy)
    cheapestBuy = cheapestBuy if cheapestBuy < value else value
return bestSell
```