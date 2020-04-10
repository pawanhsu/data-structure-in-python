<h1><center> Queue</center></h1>
## 1. Definition:
> A Queue is a linear data structure which models a real world queue by having 2 primary operation, namely "enqueue" and "dequque"

## 2. When to used:
> 1. Any waiting line models a queue(FIFO). (movie theatre, web server request waiting queue)
> 2. Breadth first search

## 3. Complexity
| Operation  |time complexity  |  
|---|---|
|Enqueue   | O(1)  |
|Dequeue   | O(1)  | 
|Peek   | O(1)  |
|Search   | O(N) |
|Is_empty   | O(1)  |

## 4. Implementation

> A Queue can be implemented mostly by array or linked list.
> 
> * noted that if implemented by fixed size array, we should handle the overflow issue.


## 5. Usage
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
