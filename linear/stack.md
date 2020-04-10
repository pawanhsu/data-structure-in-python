<h1><center> Stack</center></h1>
## 1. Definition:
> A stack is an one-ended linear data structure which models a real world stack (first in last out) by having two primary operation, namely "push" and "pop"

## 2. When to used:
> 1. Used by "Undo" something such as the undo in text editors.
> 2. Used in compiler syntax checking for matching brackets etc..
> 3. Depth first search

## 3. Complexity
| Operation  |Time Complexity   | 
|---|---|
|Pushing   | O(1)  |
|Poping  | O(1)  |
|Peeping   |O(1) |
|Size   | O(1)  |
|Searching| O(N) |
|IsEmpty   | O(1)  |

## 4. Implementation

> A Stack can be implemented mostly by array or linked list.
> 
> * noted: if implemented by static array, we need to handle the overflow issue.

```
class Stack:
    def __init__(self, x=None):
        self.arr = []
        self.size = 0
        if x is not None:
            self.push(x)
    
    def pop(self):
        if self.is_empty():
            raise Exception('stack is empty')
        ret = self.arr.pop()
        self.size -= 1
        return ret
    
    def __repr__(self):
        return 'stack: {}, size: {}'.format(self.arr, self.get_size())
        
    def push(self, x):
        self.arr.append(x)
        self.size += 1
    
    def peek(self):
        if self.is_empty():
            raise Exception('stack is empty')
        return self.arr[-1]
    
    def get_size(self):
        return self.size
    
    def is_empty(self):
        return True if not self.size else False
        
```
```
class Node:
    def __init__(self, x):
        self.data = x
        self.next = None

class LinkedListStack:
    def __init__(self, x):
        self.head = None
        self.size = 0
        if x is not None:
            self.push(x)
            
    def __repr__(self):
        head = self.head
        ret = []
        
        while head is not None:
            ret.append(str(head.data))
            head = head.next
        return 'stack: {}'.format('->'.join(ret))
            
    
    def push(self, x):
        if self.head is None:
            self.head = Node(x)
        else:
            node = Node(x)
            node.next, self.head = self.head, node
        self.size += 1
    
    def pop(self):
        if self.is_empty():
            raise Exception('stack is empty')
        ret = self.head.data
        self.head = self.head.next
        self.size -= 1
        return ret
    
    def peek(self):
        return self.head.data
    
    def get_size(self):
        return self.size
    
    def is_empty(self):
        return True if self.head is None else False
    
```
