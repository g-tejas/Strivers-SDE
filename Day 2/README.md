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

# Find The Repeating And Missing Numbers

```python
totalSum = int((len(A) * (len(A)+1))/2)
actualSum = 0

totalSumSquare = int((len(A) * (len(A) + 1) * (2*len(A) + 1))/6)
actualSumSquare = 0

for i in A:
    actualSum += i
    actualSumSquare += i**2

differenceSum = actualSum - totalSum
differenceSumSquare = (actualSumSquare - totalSumSquare)/differenceSum

missingNumber = int(abs((differenceSum - differenceSumSquare)/2))
repeatedNumber = int(differenceSumSquare - missingNumber)

```

# Number Of Inversions In An Array (Merge Sort Required)

```python
def mergeSort(arr, n):
    # A temp_arr is created to store
    # sorted array in merge function
    temp_arr = [0]*n
    return _mergeSort(arr, temp_arr, 
                      0, n - 1)
  
# This Function will use MergeSort to 
# count inversions
def _mergeSort(arr, temp_arr, left, right):
  
    # A variable inv_count is used to store
    # inversion counts in each recursive call
  
    inv_count = 0
  
    # We will make a recursive call if and 
    # only if we have more than one elements
  
    if left < right:
  
        # mid is calculated to divide the array 
        # into two subarrays
        # Floor division is must in case of python
  
        mid = (left + right)//2
  
        # It will calculate inversion 
        # counts in the left subarray
        inv_count += _mergeSort(arr, temp_arr, 
                                left, mid)
  
        # It will calculate inversion 
        # counts in right subarray
        inv_count += _mergeSort(arr, temp_arr, 
                                mid + 1, right)
  
        # It will merge two subarrays in 
        # a sorted subarray
        inv_count += merge(arr, temp_arr, 
                           left, mid, right)
    return inv_count
  
# This function will merge two subarrays 
# in a single sorted subarray
def merge(arr, temp_arr, left, mid, right):
  
    # Starting index of left subarray
    i = left     
  
    # Starting index of right subarray
    j = mid + 1 
  
    # Starting index of to be sorted subarray
    k = left     
    inv_count = 0
  
    # Conditions are checked to make sure that 
    # i and j don't exceed their
    # subarray limits.
  
    while i <= mid and j <= right:
  
        # There will be no inversion if 
        # arr[i] <= arr[j]
        if arr[i] <= arr[j]:
            temp_arr[k] = arr[i]
            k += 1
            i += 1
        else:
  
            # Inversion will occur.
            temp_arr[k] = arr[j]
            inv_count += (mid-i + 1)
            k += 1
            j += 1
  
    # Copy the remaining elements of left 
    # subarray into temporary array
    while i <= mid:
        temp_arr[k] = arr[i]
        k += 1
        i += 1
  
    # Copy the remaining elements of right 
    # subarray into temporary array
    while j <= right:
        temp_arr[k] = arr[j]
        k += 1
        j += 1
  
    # Copy the sorted subarray into 
    # Original array
    for loop_var in range(left, right + 1):
        arr[loop_var] = temp_arr[loop_var]
          
    return inv_count
  
# Driver Code
# Given array is
arr = [1, 20, 6, 4, 5]
n = len(arr)
result = mergeSort(arr, n)
print("Number of inversions are", result)

```



