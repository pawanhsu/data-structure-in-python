<h1><center> Array</center></h1>
## 1. Definition:
> A fixed or dynamic container containing n elements **indexable** from range (0, n-1)

## 2. When to used:
> 1. Storing & access sequential data
> 2. Buffering
> 3. Loop up table. (ex: dynamic programming)
> 4. Return multiple values for function call

## 3. Complexity
|   |static   |  dynamic |
|---|---|---|
|Access   | O(1)  | O(1)  |
|Search   | O(N)  | O(N)  |
|Insertion   | N/A (fixed sized)  | O(N)  |
|Appending   | N/A  | O(1)  |
|Removal   | N/A  | O(N(  |

## 4. Implementation

> The implementation for Dynamic Array can be:

> 1. Create a static array with static Capacity
> 2. Add elements to the underlying static array, keep track of the number of elements
> 3. If adding another element will exceed the capacity, then create a new array with twice size capacity and copy the original elements into it.
> 
> - Node that in python, **list** is a very powerful data structure which already implement all the operation for array. 


## 5. Usage
```
>>> arr = [1, 2, 3, 4, 7, 4, 4, 5]
>>> arr[0]
1
>>> arr.append(3)
>>> arr
[1, 2, 3, 4, 7, 4, 4, 5, 3]
>>> del arr[0] # delete by index
>>> arr
[2, 3, 4, 7, 4, 4, 5, 3]
>>> arr.remove(4) # note this will only remove 1 element from array. 
>>> arr
[2, 3, 7, 4, 4, 5, 3]
>>> arr = [e for e in arr if e != 4] # approach to remove value completely from array
>>> arr
[2, 3, 7, 5, 3]
```
