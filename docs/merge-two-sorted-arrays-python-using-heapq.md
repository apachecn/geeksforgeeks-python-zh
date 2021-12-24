# 使用 heapq

合并 Python 中的两个排序数组

> 原文:[https://www . geesforgeks . org/merge-two-sorted-arrays-python-using-heapq/](https://www.geeksforgeeks.org/merge-two-sorted-arrays-python-using-heapq/)

给定两个排序的数组，任务是以排序的方式合并它们。

示例:

```
Input :  arr1 = [1, 3, 4, 5]  
         arr2 = [2, 4, 6, 8]
Output : arr3 = [1, 2, 3, 4, 4, 5, 6, 8]

Input  : arr1 = [5, 8, 9]  
         arr2 = [4, 7, 8]
Output : arr3 = [4, 5, 7, 8, 8, 9]

```

此问题已有解决方案请参考[合并两个排序数组](https://www.geeksforgeeks.org/merge-two-sorted-arrays/)链接。我们将用 python 在一行代码中使用 **heapq.merge()** 来解决这个问题。

```
# Function to merge two sorted arrays
from heapq import merge

def mergeArray(arr1,arr2):
    return list(merge(arr1, arr2))

# Driver function
if __name__ == "__main__":
    arr1 = [1,3,4,5]  
    arr2 = [2,4,6,8]
    print (mergeArray(arr1, arr2))
```

输出:

```
[1, 2, 3, 4, 4, 5, 6, 8]

```

### heapq 模块的性质？

该模块提供了堆队列算法的实现，也称为优先级队列算法。
要创建堆，请使用初始化为[]的列表，或者可以通过函数 heapify()将填充的列表转换为堆。提供了以下功能:

*   **<u>heapq.heappush(堆，项):</u>** 将值项推送到堆上，保持堆不变。
*   **<u>heapq.heappop(堆):</u>** 从堆中弹出并返回最小的项目，保持堆不变。如果堆为空，则会引发**索引错误**。若要访问最小的项目而不弹出它，请使用堆[0]。
*   **<u>heapq . heappushppop(堆，项):</u>** 将项推上堆，然后弹出并返回堆中最小的项。组合操作比 heappush()运行效率更高，后面是对 heappop()的单独调用。
*   **<u>heapq . heapify(x):</u>**在线性时间内将列表 x 转换为堆、就地。
*   **<u>heapq.merge(*iterables) :</u>** Merge multiple sorted inputs into a single sorted output (for example, merge timestamped entries from multiple log files). Returns an iterator over the sorted values.

    本文由 [**沙莎克·米什拉(古卢)**](https://auth.geeksforgeeks.org/profile.php?user=Shashank Mishra) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。