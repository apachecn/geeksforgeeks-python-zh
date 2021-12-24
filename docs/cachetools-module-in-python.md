# Python 中的 Cachetools 模块

> 原文:[https://www.geeksforgeeks.org/cachetools-module-in-python/](https://www.geeksforgeeks.org/cachetools-module-in-python/)

**Cachetools** 是一个 Python 模块，提供各种记忆集合和装饰器。它还包括 functools 的@lru_cache 装饰器的变体。要使用它，首先，我们需要使用 pip 安装它。

```py
pip install cachetools
```

**Cachetools** 为我们提供了五个主要功能。

*   藏起
*   乌克兰语
*   TTLCache
*   lrucache
*   rcache

让我们通过例子详细了解以下每个函数。

### 藏起

**缓存的**用作装饰器。当我们调用 cache 时，它会缓存该函数以备后用。默认情况下，这将执行简单的缓存。

**语法:**

```py
@cached(cache = {})
def some_fun():
    pass

```

**示例:**我们用一个例子来看看。我们将使用时间模块来查看我们模块的效率。

```py
from cachetools import cached
import time

# Without cached
def fib(n):
    return n if n<2 else fib(n-1) + fib(n-2)

s = time.time()
print(old_fib(35))
print("Time Taken: ", time.time() - s)

# Now using cached
s = time.time()

# Use this decorator to enable caching
@cached(cache ={})
def fib(n):
    return n if n<2 else fib(n-1) + fib(n-2)

print(fib(35))
print("Time Taken(cached): ", time.time() - s)
```

**输出:**

```py
9227465
Time Taken:  4.553245782852173
9227465
Time Taken(cached):  0.0003821849822998047

```

### 乌克兰语

**LRUCache** 在缓存装饰器内部使用。LRU 缓存是指“最近最少使用”的缓存。它采用一个参数“maxsize”，该参数规定了应该如何缓存最近的函数。

**语法:**

```py
@cached(cache= LRUCache(maxsize= 3))
def some_fun():
    pass

```

**示例:**

```py
from cachetools import cached, LRUCache
import time

# cache using LRUCache
@cached(cache = LRUCache(maxsize = 3))
def myfun(n):

    # This delay resembles some task
    s = time.time()
    time.sleep(n)
    print("\nTime Taken: ", time.time() - s)
    return (f"I am executed: {n}")

# Takes 3 seconds
print(myfun(3))

# Takes no time
print(myfun(3))

# Takes 2 seconds
print(myfun(2))

# Takes 1 second
print(myfun(1))

# Takes 4 seconds
print(myfun(4))

# Takes no time
print(myfun(1))

# Takes 3 seconds because maxsize = 3 
# and the 3 recent used functions had 1,
# 2 and 4.
print(myfun(3))
```

**输出:**

```py
Time Taken:  3.0030977725982666
I am executed: 3
I am executed: 3

Time Taken:  2.002072334289551
I am executed: 2

Time Taken:  1.001115083694458
I am executed: 1

Time Taken:  4.001702070236206
I am executed: 4
I am executed: 1

Time Taken:  3.0030171871185303
I am executed: 3
```

**注意:** **LRUCache** 也可以从标准 Python 包——functools 调用。它可以被导入为

```py
from functools import lru_cache
@lru_cache
def myfunc():
    pass
```

### TTLCache

**TTLCache** 或“生存时间”缓存是 cachetools 模块中包含的第三个功能。它需要两个参数——“max size”和“TTL”。“maxsize”的使用与 LRUCache 相同，但这里“TTL”的值表示缓存应该存储多长时间。该值以秒为单位。

**语法:**

```py
@cached(cache= TTLCache(maxsize= 33, ttl = 600))
def some_fun():
    pass

```

**示例:**

```py
from cachetools import cached, TTLCache
import time

# Here recent 32 functions 
# will we stored for 1 minutes
@cached(cache = TTLCache(maxsize = 32, ttl = 60))        
def myfun(n):

    # This delay resembles some task
    s = time.time()
    time.sleep(n)
    print("\nTime Taken: ", time.time() - s)
    return (f"I am executed: {n}")

print(myfun(3))
print(myfun(3))
time.sleep(61)
print(myfun(3))
```

**输出:**

```py
Time Taken:  3.0031025409698486
I am executed: 3
I am executed: 3

Time Taken:  3.0029332637786865
I am executed: 3
```

### lrucache

**LFUCache** 或“最少使用”缓存是另一种类型的缓存技术，用于检索项目被调用的频率。它丢弃最少被调用的项目，以便在必要时腾出空间。它需要一个参数——“max size”，与 LRUCache 中的参数相同。

**语法:**

```py
@cached(cache= LFUCache(maxsize= 33))
def some_fun():
    pass

```

**示例:**

```py
from cachetools import cached, LFUCache
import time

# Here if a particular item is not called 
# within 5 successive call of the function,
# it will be discarded
@cached(cache = LFUCache(maxsize = 5))
def myfun(n):

    # This delay resembles some task
    s = time.time()
    time.sleep(n)
    print("\nTime Taken: ", time.time() - s)
    return (f"I am executed: {n}")

print(myfun(3))
print(myfun(3))
print(myfun(2))
print(myfun(4))
print(myfun(1))
print(myfun(1))
print(myfun(3))
print(myfun(3))
print(myfun(4))
```

**输出:**

```py

Time Taken:  3.002413272857666
I am executed: 3
I am executed: 3

Time Taken:  2.002107620239258
I am executed: 2

Time Taken:  4.003819465637207
I am executed: 4

Time Taken:  1.0010886192321777
I am executed: 1
I am executed: 1
I am executed: 3
I am executed: 3
I am executed: 4

```

### rcache

**RRCache** 或“随机替换”缓存是另一种类型的缓存技术，它会随机选择缓存中的项目，并在必要时将其丢弃以释放空间。它需要一个参数——“max size”，与 LRUCache 中的参数相同。它还有一个默认设置为“random.choice”的参数选项。

**语法:**

```py
@cached(cache= RRCache(maxsize= 33))
def some_fun():
    pass

```

**示例:**

```py
from cachetools import cached, RRCache
import time

# Here if a particular item is not called
# within 5 successive call of the function,
# it will be discarded
@cached(cache = RRCache(maxsize = 5))
def myfun(n):

    # This delay resembles some task
    s = time.time()
    time.sleep(n)
    print("\nTime Taken: ", time.time() - s)
    return (f"I am executed: {n}")

print(myfun(3))
print(myfun(3))
print(myfun(2))
print(myfun(4))
print(myfun(1))
print(myfun(1))
print(myfun(3))
print(myfun(2))
print(myfun(3))
```

**输出:**

```py
Time Taken:  3.003124713897705
I am executed: 3
I am executed: 3

Time Taken:  2.0021231174468994
I am executed: 2

Time Taken:  4.004120588302612
I am executed: 4

Time Taken:  1.0011250972747803
I am executed: 1
I am executed: 1
I am executed: 3
I am executed: 2
I am executed: 3

```