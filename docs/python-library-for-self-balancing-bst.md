# 用于自平衡 BST 的 Python 库

> 原文:[https://www . geesforgeks . org/python-library-for-self-balance-BST/](https://www.geeksforgeeks.org/python-library-for-self-balancing-bst/)

这里我们将看到模拟库框架 [TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) ，它在 Python 上的 Java 中是可用的。存在不允许重复条目的情况，特别是在任何管理软件中，其中对象通过其唯一性被唯一地识别。在这篇文章中，让我们看看如何以皮托尼克的方式做到这一点。
在我们的实现中，“树集合”类是一个类似于 Java 树集合的二叉树集合。添加/删除元素时，树集将自动排序。不会添加重复的元素。
包含的功能有:

*   将元素插入到树集中。
*   将多个元素插入到树集中。
*   从树集中获取天花板值。
*   从树集中获取地板值。
*   从树集中删除元素。
*   从树集中删除所有元素。
*   获取树集合的浅拷贝。
*   从树集中弹出一个元素。

## 蟒蛇 3

```
# The bisect module ensures the automatic sort after insertion
import bisect

class TreeSet(object):
    """
    Binary-tree set like java Treeset.
    Duplicate elements will not be added.
    When added new element, TreeSet will be
    sorted automatically.
    """
    def __init__(self, elements):
        self._treeset = []
        self.addAllElements(elements)

    # To add many elements
    def addAllElements(self, elements):
        for element in elements:
            if element in self: continue
            self.addElement(element)

    # To add an element
    def addElement(self, element):
        if element not in self:
            bisect.insort(self._treeset, element)

    # To get ceiling value
    def ceiling(self, e):
        index = bisect.bisect_right(self._treeset, e)
        if self[index - 1] == e:
            return e
        return self._treeset[bisect.bisect_right(self._treeset, e)]

    def floor(self, e):
        index = bisect.bisect_left(self._treeset, e)
        if self[index] == e:
            return e
        else:
            return self._treeset[bisect.bisect_left(self._treeset, e) - 1]

    def __getitem__(self, num):
        return self._treeset[num]

    def __len__(self):
        return len(self._treeset)

    def clearElements(self):
        """
        Delete all elements in TreeSet.
        """
        self._treeset = []

    def clone(self):
        """
        Return shallow copy of self.
        """
        return TreeSet(self._treeset)

    def removeElement(self, element):
        """
        Remove element if element in TreeSet.
        """
        try:
            self._treeset.remove(element)
        except ValueError:
            return False
        return True

    def __iter__(self):
        """
        Do ascending iteration for TreeSet
        """
        for element in self._treeset:
            yield element

    def pop(self, index):
        return self._treeset.pop(index)

    def __str__(self):
        return str(self._treeset)

    def __eq__(self, target):
        if isinstance(target, TreeSet):
            return self._treeset == target.treeset
        elif isinstance(target, list):
            return self._treeset == target

    def __contains__(self, e):
        """
        Fast attribution judgement by bisect
        """
        try:
            return e == self._treeset[bisect.bisect_left(self._treeset, e)]
        except:
            return False

if __name__ == '__main__':
    treeSet = TreeSet([3, 7, 7, 1, 3, 10])

    # As there is no 5, floor of this gives the
    # next least value  in the treeset i.e. 3
    print("treeSet.floor(5) : ", treeSet.floor(5))

    # As there is no 4, ceil of this gives the
    # next highest value in the treeset i.e. 7
    print("treeSet.ceiling(4) : ", treeSet.ceiling(4))

    # As there is no 2, floor of this gives the next
    # least value  in the treeset i.e. 1
    print("treeSet.floor(2) : ", treeSet.floor(2))

    # As there is 3, ceil will give 3 as it is
    print("treeSet.ceiling(3) : ", treeSet.ceiling(3)) 

    # As there is 10, floor will give 10 as it is
    print("treeSet.floor(10) : ", treeSet.floor(10)) 

    # No duplicates printed
    print("treeSet : ", treeSet)

    # 2nd example
    treeSet = TreeSet([30, 70, 20, 70, 10, 30])

    # No duplicates printed
    print("2nd example treeSet :", treeSet)

    treeSet.addElement(40)
    print("Adding 40 to the above, it is arranged in\
    sorted order : ", treeSet)

    treeSet.removeElement(70)
    print("After removing 70 ", treeSet)

    treeSet.removeElement(50)
    print("After removing 50, no issue even if not\
    available ", treeSet) 
    # There is no 50 available

    treeSet.addAllElements([30, 40, 50, 60])
    print("After adding many elements, duplicate are\
    not taken :", treeSet)

    # Getting first element of treeset
    print(treeSet[0])

    # See, how elements can be retrieved
    print(treeSet[-1], treeSet[5], treeSet[-2],
          treeSet[-3], treeSet[-4], treeSet[-5])

    # Check for the existence of 10 and since
    # found, it returns true
    print(10 in treeSet)

    # Check for the existence of 100 and since
    # not found, it returns false
    print(100 in treeSet)

    for i in TreeSet([10, 30, 40]):
        print(i)  
```

**输出:**

> treeSet . floor(5):3
> treeSet . ceiling(4):7
> treeSet . floor(2):1
> treeSet . ceiling(3):3
> treeSet . floor(10):10
> treeSet:【1，3，7，10】
> treeSet:【10，20，30，70】
> 以上加 40，按排序顺序排列:【10，20，30，40，70】
> 去掉 70 后