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
