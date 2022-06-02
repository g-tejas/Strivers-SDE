# Reverse Linked List

```python

prev, curr = None, head
while curr:
    curr.next, prev, curr = prev, curr, curr.next
return prev

```

# Find The Middle Of Linked List

```python

slow = fast = head
while fast and fast.next:
    slow = slow.next
    fast = fast.next.next
return slow

```
