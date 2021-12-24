# Python 中的最大堆

> 原文:[https://www.geeksforgeeks.org/max-heap-in-python/](https://www.geeksforgeeks.org/max-heap-in-python/)

A [Max-Heap](https://www.geeksforgeeks.org/binary-heap/) 是一个完整的二叉树，其中每个内部节点中的值大于或等于该节点的子节点中的值。
将一个堆的元素映射到一个数组是很简单的:如果一个节点存储了一个索引 k，那么它的左子节点存储在索引 **2k + 1** 处，它的右子节点存储在索引 **2k + 2** 处。

**Max Heap 示例:**

![max-heap](img/3a68c0b7e894e84fb6348ab61291f532.png)

**Max Heap 是如何表现的？**
最大堆是一棵完整的二叉树。最大堆通常表示为一个数组。根元素将位于`Arr[0]`。下表显示了第 ith 个节点的其他节点的索引，即: `Arr[i]` :
`Arr[(i-1)/2]`返回父节点。
`Arr[(2*i)+1]`返回左侧子节点。
`Arr[(2*i)+2]`返回右子节点。

## 最大堆上的操作:

1.  **getMax()** :返回 Max Heap 的根元素。该操作的时间复杂度为 **O(1)** 。
2.  **提取最大值()**:从最大堆中移除最大元素。该操作的时间复杂度为 **O(Log n)** ，因为该操作需要在移除根后维护堆属性(通过调用 heapify())。
3.  **插入()**:插入新钥匙需要 **O(Log n)** 时间。我们在树的末端添加一个新的键。如果新密钥比它的父密钥小，那么我们不需要做任何事情。否则，我们需要遍历以修复违反的堆属性。

**注意:**在下面的实现中，我们从索引 1 开始做索引，以简化实现。

```
# Python3 implementation of Max Heap
import sys

class MaxHeap:

    def __init__(self, maxsize):

        self.maxsize = maxsize
        self.size = 0
        self.Heap = [0] * (self.maxsize + 1)
        self.Heap[0] = sys.maxsize
        self.FRONT = 1

    # Function to return the position of
    # parent for the node currently
    # at pos
    def parent(self, pos):

        return pos // 2

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

        self.Heap[fpos], self.Heap[spos] = (self.Heap[spos], 
                                            self.Heap[fpos])

    # Function to heapify the node at pos
    def maxHeapify(self, pos):

        # If the node is a non-leaf node and smaller
        # than any of its child
        if not self.isLeaf(pos):
            if (self.Heap[pos] < self.Heap[self.leftChild(pos)] or
                self.Heap[pos] < self.Heap[self.rightChild(pos)]):

                # Swap with the left child and heapify
                # the left child
                if (self.Heap[self.leftChild(pos)] > 
                    self.Heap[self.rightChild(pos)]):
                    self.swap(pos, self.leftChild(pos))
                    self.maxHeapify(self.leftChild(pos))

                # Swap with the right child and heapify
                # the right child
                else:
                    self.swap(pos, self.rightChild(pos))
                    self.maxHeapify(self.rightChild(pos))

    # Function to insert a node into the heap
    def insert(self, element):

        if self.size >= self.maxsize:
            return
        self.size += 1
        self.Heap[self.size] = element

        current = self.size

        while (self.Heap[current] > 
               self.Heap[self.parent(current)]):
            self.swap(current, self.parent(current))
            current = self.parent(current)

    # Function to print the contents of the heap
    def Print(self):

        for i in range(1, (self.size // 2) + 1):
            print(" PARENT : " + str(self.Heap[i]) + 
                  " LEFT CHILD : " + str(self.Heap[2 * i]) +
                  " RIGHT CHILD : " + str(self.Heap[2 * i + 1]))

    # Function to remove and return the maximum
    # element from the heap
    def extractMax(self):

        popped = self.Heap[self.FRONT]
        self.Heap[self.FRONT] = self.Heap[self.size]
        self.size -= 1
        self.maxHeapify(self.FRONT)

        return popped

# Driver Code
if __name__ == "__main__":

    print('The maxHeap is ')

    maxHeap = MaxHeap(15)
    maxHeap.insert(5)
    maxHeap.insert(3)
    maxHeap.insert(17)
    maxHeap.insert(10)
    maxHeap.insert(84)
    maxHeap.insert(19)
    maxHeap.insert(6)
    maxHeap.insert(22)
    maxHeap.insert(9)

    maxHeap.Print()

    print("The Max val is " + str(maxHeap.extractMax()))
```

**输出:**

```
The maxHeap is 
 PARENT : 84 LEFT CHILD : 22 RIGHT CHILD : 19
 PARENT : 22 LEFT CHILD : 17 RIGHT CHILD : 10
 PARENT : 19 LEFT CHILD : 5 RIGHT CHILD : 6
 PARENT : 17 LEFT CHILD : 3 RIGHT CHILD : 9
The Max val is 84

```

## 使用库函数:

我们使用 [heapq](https://www.geeksforgeeks.org/heap-queue-or-heapq-in-python/) 类来实现 Python 中的 Heaps。默认情况下，最小堆由这个类实现。但是我们将每个值乘以-1，这样我们就可以将其用作 MaxHeap。

```
# Python3 program to demonstrate working of heapq

from heapq import heappop, heappush, heapify

# Creating empty heap
heap = []
heapify(heap)

# Adding items to the heap using heappush
# function by multiplying them with -1
heappush(heap, -1 * 10)
heappush(heap, -1 * 30)
heappush(heap, -1 * 20)
heappush(heap, -1 * 400)

# printing the value of maximum element
print("Head value of heap : "+str(-1 * heap[0]))

# printing the elements of the heap
print("The heap elements : ")
for i in heap:
    print(-1 * i, end = ' ')
print("\n")

element = heappop(heap)

# printing the elements of the heap
print("The heap elements : ")
for i in heap:
    print(-1 * i, end = ' ')
```

**输出:**

```
Head value of heap : 400
The heap elements : 
400 30 20 10 

The heap elements : 
30 10 20 

```