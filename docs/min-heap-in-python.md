# Python 中的最小堆

> 原文:[https://www.geeksforgeeks.org/min-heap-in-python/](https://www.geeksforgeeks.org/min-heap-in-python/)

A [Min-Heap](https://www.geeksforgeeks.org/binary-heap/) 是一个完整的二叉树，其中每个内部节点中的值小于或等于该节点的子节点中的值。
将一个堆的元素映射成一个数组并不重要:如果一个节点存储在索引 k，那么它的左子节点存储在索引 **2k + 1** 处，它的右子节点存储在索引 **2k + 2** 处。

**最小堆示例:**

```
            5                      13
         /      \               /       \  
       10        15           16         31 
      /                      /  \        /  \
    30                     41    51    100   41
```

**Min Heap 是如何表现的？**
最小堆是一棵完整的二叉树。最小堆通常表示为一个数组。根元素将位于**Arr【0】**。对于任何 ith 节点，即**Arr【I】**:

*   **Arr[(i -1) / 2]** 返回其父节点。
*   **Arr[(2 * i) + 1]** 返回其左子节点。
*   **Arr[(2 * i) + 2]** 返回其右子节点。

**最小堆上的操作:**

1.  **getMin()** :返回 Min 堆的根元素。该操作的时间复杂度为 **O(1)** 。
2.  **extractMin()** :从 MinHeap 中移除最小元素。该操作的时间复杂度为 **O(Log n)** ，因为该操作需要在移除根后维护堆属性(通过调用 heapify())。
3.  **插入()**:插入新钥匙需要 **O(Log n)** 时间。我们在树的末端添加一个新的键。如果新密钥比它的父密钥大，那么我们不需要做任何事情。否则，我们需要遍历以修复违反的堆属性。

下面是 Python 中最小堆的实现——

## 蟒蛇 3

```
# Python3 implementation of Min Heap

import sys

class MinHeap:

    def __init__(self, maxsize):
        self.maxsize = maxsize
        self.size = 0
        self.Heap = [0]*(self.maxsize + 1)
        self.Heap[0] = -1 * sys.maxsize
        self.FRONT = 1

    # Function to return the position of
    # parent for the node currently
    # at pos
    def parent(self, pos):
        return pos//2

    # Function to return the position of
    # the left child for the node currently
    # at pos
    def leftChild(self, pos):
        return 2 * pos

    # Function to return the position of
    # the right child for the node currently
    # at pos
    def rightChild(self, pos):
        return (2 * pos) + 1

    # Function that returns true if the passed
    # node is a leaf node
    def isLeaf(self, pos):
        if pos >= (self.size//2) and pos <= self.size:
            return True
        return False

    # Function to swap two nodes of the heap
    def swap(self, fpos, spos):
        self.Heap[fpos], self.Heap[spos] = self.Heap[spos], self.Heap[fpos]

    # Function to heapify the node at pos
    def minHeapify(self, pos):

        # If the node is a non-leaf node and greater
        # than any of its child
        if not self.isLeaf(pos):
            if (self.Heap[pos] > self.Heap[self.leftChild(pos)] or
               self.Heap[pos] > self.Heap[self.rightChild(pos)]):

                # Swap with the left child and heapify
                # the left child
                if self.Heap[self.leftChild(pos)] < self.Heap[self.rightChild(pos)]:
                    self.swap(pos, self.leftChild(pos))
                    self.minHeapify(self.leftChild(pos))

                # Swap with the right child and heapify
                # the right child
                else:
                    self.swap(pos, self.rightChild(pos))
                    self.minHeapify(self.rightChild(pos))

    # Function to insert a node into the heap
    def insert(self, element):
        if self.size >= self.maxsize :
            return
        self.size+= 1
        self.Heap[self.size] = element

        current = self.size

        while self.Heap[current] < self.Heap[self.parent(current)]:
            self.swap(current, self.parent(current))
            current = self.parent(current)

    # Function to print the contents of the heap
    def Print(self):
        for i in range(1, (self.size//2)+1):
            print(" PARENT : "+ str(self.Heap[i])+" LEFT CHILD : "+
                                str(self.Heap[2 * i])+" RIGHT CHILD : "+
                                str(self.Heap[2 * i + 1]))

    # Function to build the min heap using
    # the minHeapify function
    def minHeap(self):

        for pos in range(self.size//2, 0, -1):
            self.minHeapify(pos)

    # Function to remove and return the minimum
    # element from the heap
    def remove(self):

        popped = self.Heap[self.FRONT]
        self.Heap[self.FRONT] = self.Heap[self.size]
        self.size-= 1
        self.minHeapify(self.FRONT)
        return popped

# Driver Code
if __name__ == "__main__":

    print('The minHeap is ')
    minHeap = MinHeap(15)
    minHeap.insert(5)
    minHeap.insert(3)
    minHeap.insert(17)
    minHeap.insert(10)
    minHeap.insert(84)
    minHeap.insert(19)
    minHeap.insert(6)
    minHeap.insert(22)
    minHeap.insert(9)
    minHeap.minHeap()

    minHeap.Print()
    print("The Min val is " + str(minHeap.remove()))
```

**输出:**

```
The Min Heap is 
 PARENT : 3 LEFT CHILD : 5 RIGHT CHILD :6
 PARENT : 5 LEFT CHILD : 9 RIGHT CHILD :84
 PARENT : 6 LEFT CHILD : 19 RIGHT CHILD :17
 PARENT : 9 LEFT CHILD : 22 RIGHT CHILD :10
The Min val is 3
```

## 使用库函数:

我们使用 [heapq](https://www.geeksforgeeks.org/heap-queue-or-heapq-in-python/) 类来实现 Python 中的 Heaps。默认情况下，最小堆由这个类实现。

## 蟒蛇 3

```
# Python3 program to demonstrate working of heapq

from heapq import heapify, heappush, heappop

# Creating empty heap
heap = []
heapify(heap)

# Adding items to the heap using heappush function
heappush(heap, 10)
heappush(heap, 30)
heappush(heap, 20)
heappush(heap, 400)

# printing the value of minimum element
print("Head value of heap : "+str(heap[0]))

# printing the elements of the heap
print("The heap elements : ")
for i in heap:
    print(i, end = ' ')
print("\n")

element = heappop(heap)

# printing the elements of the heap
print("The heap elements : ")
for i in heap:
    print(i, end = ' ')
```

**输出:**

```
Head value of heap : 10
The heap elements : 
10 30 20 400 

The heap elements : 
20 30 400
```