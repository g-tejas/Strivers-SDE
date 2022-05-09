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