# 在 Python 中实现 LRU 缓存装饰器

> 原文:[https://www . geesforgeks . org/impering-LRU-cache-decorator-in-python/](https://www.geeksforgeeks.org/implementing-lru-cache-decorator-in-python/)

[LRU](https://www.geeksforgeeks.org/lru-cache-implementation/) 是删除最近最少使用的数据并存储新数据的缓存替换算法。假设我们有 10 个内存帧的缓存空间。并且每一帧都填充了一个文件。现在，如果我们想要存储新文件，我们需要删除缓存中最旧的文件并添加新文件。这就是 LRU 的工作方式。
**LRU 缓存由 Queue 和 Dictionary 数据结构组成。**

*   **队列:**存储最近使用到最近最少使用的文件

*   **哈希表:**存储文件及其在缓存中的位置

> **参考以下文章获取更多主题信息:**
> 
> *   [蟒蛇和 LRU 缓存](https://www.geeksforgeeks.org/python-lru-cache/)
>     
> *   [LRU 缓存实现](https://www.geeksforgeeks.org/lru-cache-implementation/)T2】

### 什么是装饰师？

一个[装饰器](http://geeksforgeeks.org/decorators-in-python/)是一个把一个函数作为其唯一参数并返回一个函数的函数。这有助于一次又一次地用相同的代码“包装”功能。
**注:**更多信息，请参考 Python 中的[装饰器](http://geeksforgeeks.org/decorators-in-python/)。
现在，在了解了 Python 中的 LRU 和装饰器的基本概念之后，让我们来看看 Python 中的 LRU 缓存装饰器的实现。

## 蟒蛇 3

```py
from collections import deque

# LRU cache implementation
class LRUCache:

    def __init__(self, size=5):
        self.size = size
        self.container = deque()
        self.map = dict()

    def reallocate(self):
        # to reallocate the hashmap for
        # every access of file access file
        # will reallocate the data in hashmap
        # according to the numbers position
        # in the container for every access,
        # hit and miss(evict)
        if len(self.container) > 1:

            for key, val in enumerate(self.container):
                self.map[val] = key

    def access(self, val):

        # print("access "+str(val))
        self.container.remove(val)
        self.container.appendleft(val)
        self.reallocate()

    def evict(self, val):

        # print("cache miss "+str(val))
        if val in self.map:
            #del self.map[val]
            self.container.remove(val)

        else:
            x = self.container.pop()
            del self.map[x]

        self.normal_insert(val)

    def normal_insert(self, val):
        self.container.appendleft(val)
        self.reallocate()

    def insert(self, val):

        if val in self.map.keys():

            # if value in present in
            # the hashmap then it is a hit.
            # access function will access the
            # number already present and replace
            # it to leftmost position
            self.access(val)

        else:
            # if value is not present in
            # the hashtable
            if (len(self.map.keys()) == self.size):
                # if the size of the queue
                # is equal to capacity and
                # we try to insert the number,
                # then it is a miss then,
                # evict function will delete the
                # right most elements and insert
                # the latest element in the
                # leftmost position
                self.evict(val)

            else:
                # normal_insert function will normally
                # insert the data into the cache..
                self.normal_insert(val)

    def print(self):
        lru_elements = [x for x in self.container]
        print(lru_elements)

# definition of lru decorator
def LRUDecorator(size):

    lru = LRUCache(size)

    def decorator(function):

        def functionality(num):
            lru.insert(num)
            lru.print()

            # to check the num pageframe(position)
            # uncomment the below statement
            # print(lur.map)
            print(num, function(num))
        return functionality

    return decorator

# Using LRU Decorator
@LRUDecorator(size=4)
def ex_func_01(n):
    print(f'Computing...{n}')
    time.sleep(1)
    return n

print(f'\nFunction: ex_func_01')
print(ex_func_01(1))
print(ex_func_01(2))
print(ex_func_01(3))
print(ex_func_01(4))
print(ex_func_01(1))
print(ex_func_01(2))
print(ex_func_01(5))
print(ex_func_01(1))
print(ex_func_01(2))
print(ex_func_01(3))
print(ex_func_01(4))
print(ex_func_01(5))
```

**输出:**

```py
Function: ex_func_01
[1]
Computing...1
1 1
None
[2, 1]
Computing...2
2 2
None
[3, 2, 1]
Computing...3
3 3
None
[4, 3, 2, 1]
Computing...4
4 4
None
[1, 4, 3, 2]
Computing...1
1 1
None
[2, 1, 4, 3]
Computing...2
2 2
None
[5, 2, 1, 4]
Computing...5
5 5
None
[1, 5, 2, 4]
Computing...1
1 1
None
[2, 1, 5, 4]
Computing...2
2 2
None
[3, 2, 1, 5]
Computing...3
3 3
None
[4, 3, 2, 1]
Computing...4
4 4
None
[5, 4, 3, 2]
Computing...5
5 5
None
```