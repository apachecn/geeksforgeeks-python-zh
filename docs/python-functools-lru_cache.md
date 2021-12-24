# Python 函式工具–LRU _ cache()

> 哎哎哎::1230【https://www . geeksforgeeks . org/python-functtools-LRU _ cache/

Python 中的**functiontools**模块处理更高阶的函数，也就是对函数进行操作(作为参数)或返回函数以及其他此类可调用对象的函数。functools 模块提供了多种方法，如`cached_property(func), cmp_to_key(func), lru_cache(func), wraps(func),`等。值得注意的是，这些方法以函数作为参数。

## lru_cache()

`lru_cache()`是**功能工具**模块中的一个这样的功能，它通过使用记忆技术来帮助减少功能的执行时间。

> **语法:**
> @lru_cache(maxsize=128，typed = False)
> 
> **参数:**
> **maxsize:** 此参数设置缓存的大小，缓存最多可以存储 maxsize 最近的函数调用，如果 maxsize 设置为 None，LRU 功能将被禁用，缓存可以无限制增长
> **类型化:**
> 如果 type 设置为 True，不同类型的函数参数将被分别缓存。例如，f(3)和 f(3.0)将被视为具有不同结果的不同调用，它们将被存储在缓存中的两个独立条目中

**例:1**

```
from functools import lru_cache
import time

# Function that computes Fibonacci 
# numbers without lru_cache
def fib_without_cache(n):
    if n < 2:
        return n
    return fib_without_cache(n-1) + fib_without_cache(n-2)

# Execution start time
begin = time.time()
fib_without_cache(30)

# Execution end time
end = time.time()

print("Time taken to execute the\
function without lru_cache is", end-begin)

# Function that computes Fibonacci
# numbers with lru_cache
@lru_cache(maxsize = 128)
def fib_with_cache(n):
    if n < 2:
        return n
    return fib_with_cache(n-1) + fib_with_cache(n-2)

begin = time.time()
fib_with_cache(30)
end = time.time()

print("Time taken to execute the \
function with lru_cache is", end-begin)
```

**输出:**

> 在没有 lru_cache 的情况下执行该函数所花费的时间是 0.4448213577270508
> 在有 lru_cache 的情况下执行该函数所花费的时间是 2.44828888005

**例 2:**

```
from functools import lru_cache

@lru_cache(maxsize = 100)
def count_vowels(sentence):
    sentence = sentence.casefold()
    return sum(sentence.count(vowel) for vowel in 'aeiou')

print(count_vowels("Welcome to Geeksforgeeks"))
```

**输出:**

```
9

```