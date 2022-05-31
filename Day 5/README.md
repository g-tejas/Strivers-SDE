# Reverse Linked List

```python

prev, curr = None, head
while curr:
    curr.next, prev, curr = prev, curr, curr.next
return prev

```