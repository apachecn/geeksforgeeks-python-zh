# Python 中使用 OrderedDict 的 LRU 缓存

> 原文:[https://www . geeksforgeeks . org/LRU-cache-in-python-using-ordereddct/](https://www.geeksforgeeks.org/lru-cache-in-python-using-ordereddict/)

[LRU(最近最少使用)缓存](https://www.geeksforgeeks.org/lru-cache-implementation/)首先丢弃最近最少使用的项目。这种算法需要跟踪什么时候使用了什么，如果想确保算法总是丢弃最近最少使用的项目，这是很昂贵的。该技术的一般实现需要为高速缓存行保留“老化位”，并基于老化位跟踪“最近最少使用”的高速缓存行。
我们的问题陈述是为最近最少使用(LRU)缓存设计和实现一个数据结构。
应支持以下操作:取放。
* **获取(密钥)**–如果密钥存在于缓存中，则获取密钥的值(将始终为正)，否则返回-1。
* **放入(键，值)**–如果键不存在，设置或插入值。当缓存达到其容量时，它应该在插入新项目之前使最近最少使用的项目无效。
缓存总是以正容量初始化。

**例:**

```
Input/Output : 
LRUCache cache = new LRUCache( 2 /* capacity */ );

cache.put(1, 1);                                    
cache.put(2, 2);
cache.get(1);       // returns 1
cache.put(3, 3);    // evicts key 2
cache.get(2);       // returns -1 (not found)
cache.put(4, 4);    // evicts key 1
cache.get(1);       // returns -1 (not found)
cache.get(3);       // returns 3
cache.get(4);       // returns 4

```

我们的解决方案是使用集合模块中[ordereddct](https://www.geeksforgeeks.org/ordereddict-in-python/)的能力，集合模块保持键的插入顺序，如果需要，我们可以更改该顺序。最好的部分是所有操作都有 O(1)的时间复杂度。
我们维护订单的方式是，订单显示最近使用订单的时间。开始时，我们会使用最近最少的，最后，使用最近最多的。
如果对某个键进行了任何更新或查询，它将移动到最后(最近使用的)。如果添加了任何内容，则在末尾添加(最近使用/添加的)
对于 get(key):我们返回在 O(1)中查询的键的值，如果在 out dict/cache 中找不到键，则返回-1。并且还将键移动到最后，以显示它最近被使用过。
对于 put(key，value):首先，我们通过常规方法添加/更新 key。并且还将键移动到最后，以显示它最近被使用过。但是在这里，我们还将检查我们的有序字典的长度是否已经超过了我们的容量，如果是，我们删除第一个键(最近最少使用的)

## 蟒蛇 3

```
from collections import OrderedDict

class LRUCache:

    # initialising capacity
    def __init__(self, capacity: int):
        self.cache = OrderedDict()
        self.capacity = capacity

    # we return the value of the key
    # that is queried in O(1) and return -1 if we
    # don't find the key in out dict / cache.
    # And also move the key to the end
    # to show that it was recently used.
    def get(self, key: int) -> int:
        if key not in self.cache:
            return -1
        else:
            self.cache.move_to_end(key)
            return self.cache[key]

    # first, we add / update the key by conventional methods.
    # And also move the key to the end to show that it was recently used.
    # But here we will also check whether the length of our
    # ordered dictionary has exceeded our capacity,
    # If so we remove the first key (least recently used)
    def put(self, key: int, value: int) -> None:
        self.cache[key] = value
        self.cache.move_to_end(key)
        if len(self.cache) > self.capacity:
            self.cache.popitem(last = False)

# RUNNER
# initializing our cache with the capacity of 2
cache = LRUCache(2)

cache.put(1, 1)
print(cache.cache)
cache.put(2, 2)
print(cache.cache)
cache.get(1)
print(cache.cache)
cache.put(3, 3)
print(cache.cache)
cache.get(2)
print(cache.cache)
cache.put(4, 4)
print(cache.cache)
cache.get(1)
print(cache.cache)
cache.get(3)
print(cache.cache)
cache.get(4)
print(cache.cache)

#This code was contributed by Sachin Negi
```

**Output:** 

```
OrderedDict([(1, 1)])
OrderedDict([(1, 1), (2, 2)])
OrderedDict([(2, 2), (1, 1)])
OrderedDict([(1, 1), (3, 3)])
OrderedDict([(1, 1), (3, 3)])
OrderedDict([(3, 3), (4, 4)])
OrderedDict([(3, 3), (4, 4)])
OrderedDict([(4, 4), (3, 3)])
OrderedDict([(3, 3), (4, 4)])

```

时间复杂度:O(1)
[LRU 其他实现](https://www.geeksforgeeks.org/lru-cache-implementation/)