# 清除 Python 中的 LRU 缓存

> 原文:[https://www.geeksforgeeks.org/clear-lru-cache-in-python/](https://www.geeksforgeeks.org/clear-lru-cache-in-python/)

是最近使用最少的缓存。LRU 缓存是一种高速内存，用于加快常用数据的检索速度。它是在队列和哈希数据结构的帮助下实现的。

注:更多信息请参考[Python-LRU 缓存](https://www.geeksforgeeks.org/python-lru-cache/)

## 如何用 Python 与 LRU 缓存交互？

从 Python 3.2 开始，Python 的**功能工具**模块就提供了与 LRU 缓存交互的功能。functool 模块提供了一个装饰器，可以放在 Python 中函数类的顶部。当在需要大量变量访问和更改操作的函数上使用时，使用 LRU 缓存可以提供巨大的速度提升。

**示例:**

```py
import functools

@functools.lru_cache(maxsize = None)
def gfg():
    # insert function logic here
    pass
```

或者，最大尺寸可以改变，以适应自己的喜好。该值以 kbs 为单位，maxsize 采用整数参数

## 清除 LRU 缓存

使用缓存后，cache_clear()可用于清除缓存或使其无效。

**例 1:**

```py
import functools

@functools.lru_cache(maxsize = None)
def fib(n): 
    if n < 2: 
        return n 
    return fib(n-1) + fib(n-2)

fib(30)

# Before Clearing
print(fib.cache_info())

fib.cache_clear()

# After Clearing
print(fib.cache_info())
```

**输出:**

```py
CacheInfo(hits=28, misses=31, maxsize=None, currsize=31)
CacheInfo(hits=0, misses=0, maxsize=None, currsize=0)
```

**示例 2:** 此外，还可以从另一个函数调用 cache_clear()

```py
import functools

@functools.lru_cache(maxsize = None)
def fib(n): 
    if n < 2: 
        return n 
    return fib(n-1) + fib(n-2)

def gfg():
    fib.cache_clear()

fib(30)

# Before Clearing
print(fib.cache_info())

gfg()

# After Clearing
print(fib.cache_info())
```

**输出:**

```py
CacheInfo(hits=28, misses=31, maxsize=None, currsize=31)
CacheInfo(hits=0, misses=0, maxsize=None, currsize=0)
```

这些方法有局限性，因为它们是个性化的，必须为每个使用该函数的 LRU 缓存键入 cache_clear()函数。我们可以通过使用 Python 内置的垃圾收集模块来收集所有具有 LRU 缓存包装器的对象，并迭代清除每个对象的缓存来克服这个问题。

**示例:**

```py
import gc
import functools

@functools.lru_cache(maxsize = None)
def gfg():
    # insert function logic here
    pass

@functools.lru_cache(maxsize = None)
def gfg1():
    # insert function logic here
    pass

@functools.lru_cache(maxsize = None)
def gfg2():
    # insert function logic here
    pass

gfg()
gfg1()
gfg2()

gc.collect()

# All objects collected
objects = [i for i in gc.get_objects() 
           if isinstance(i, functools._lru_cache_wrapper)]

# All objects cleared
for object in objects:
    object.cache_clear()
```