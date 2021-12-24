# Python 中的垃圾收集

> 原文:[https://www.geeksforgeeks.org/garbage-collection-python/](https://www.geeksforgeeks.org/garbage-collection-python/)

Python 的内存分配和解除分配方法是自动的。用户不必像在 C 或 C++等语言中使用动态内存分配那样预先分配或释放内存。
Python 使用两种内存分配策略:

*   参考计数
*   碎片帐集

在 Python 2.0 版本之前，Python 解释器只使用引用计数进行内存管理。引用计数的工作原理是计算一个对象被系统中其他对象引用的次数。当移除对对象的引用时，对象的引用计数将减少。当引用计数变为零时，对象被解除分配。从；外；离；除；超过；以前的

## 计算机编程语言

```
# Literal 9 is an object
b = 9

# Reference count of object 9
# becomes 0.
b = 4
```

文字值 9 是一个对象。对象 9 的引用计数在第 1 行增加到 1。在第 2 行中，它的引用计数在被取消引用时变为零。所以垃圾收集器会释放对象。
当对象的参考计数无法达到时，创建一个参考周期。涉及列表、元组、实例、类、字典和函数的引用循环很常见。创建引用循环最简单的方法是创建一个引用自身的对象，如下例所示:

## 计算机编程语言

```
def create_cycle():

    # create a list x
    x = [ ]

    # A reference cycle is created
    # here as x contains reference to
    # to self.
    x.append(x)

create_cycle()
```

因为 create_cycle()创建了一个引用自身的对象 x，所以当函数返回时，对象 x 不会被自动释放。这将导致 x 正在使用的内存被保留，直到 Python 垃圾收集器被调用。

### **使对象符合垃圾收集条件的方法**

## 计算机编程语言

```
x = []
x.append(l)
x.append(2)

# delete the list from memory or
# assigning object x to None(Null)
del x
# x = None
```

创建的列表的引用计数现在是两个。但是，由于它不能从 Python 内部到达，也不可能被再次使用，因此被认为是垃圾。在 Python 的当前版本中，这个列表永远不会被释放。

### **循环自动垃圾收集**

因为引用周期需要计算工作来发现，所以垃圾收集必须是一个预定的活动。Python 基于对象分配和对象释放的阈值来调度垃圾收集。当分配数减去解除分配数大于阈值数时，垃圾收集器运行。可以通过导入 gc 模块并询问垃圾收集阈值来检查新对象(Python 中称为第 0 代对象的对象)的阈值:

## 计算机编程语言

```
# loading gc
import gc

# get the current collection
# thresholds as a tuple
print("Garbage collection thresholds:",
                    gc.get_threshold())
```

**输出:**

```
Garbage collection thresholds: (700, 10, 10) 
```

这里，上述系统的默认阈值是 700。这意味着当分配数与解除分配数之比大于 700 时，自动垃圾收集器将运行。因此，您的代码中释放大块内存的任何部分都是运行手动垃圾收集的良好候选。

### **手动垃圾收集**

在程序执行期间手动调用垃圾收集器对于如何处理被引用周期消耗的内存是一个好主意。
垃圾收集可以通过以下方式手动调用:

## 计算机编程语言

```
# Importing gc module
import gc

# Returns the number of
# objects it has collected
# and deallocated
collected = gc.collect()

# Prints Garbage collector
# as 0 object
print("Garbage collector: collected",
          "%d objects." % collected)
```

**输出:**

```
('Garbage collector: collected', '0 objects.')
```

如果创建的周期很少，那么手动收集是如何工作的:
**示例:**

## 计算机编程语言

```
import gc
i = 0

# create a cycle and on each iteration x as a dictionary
# assigned to 1
def create_cycle():
    x = { }
    x[i+1] = x
    print x

# lists are cleared whenever a full collection or
# collection of the highest generation (2) is run
collected = gc.collect() # or gc.collect(2)
print "Garbage collector: collected %d objects." % (collected)

print "Creating cycles..."
for i in range(10):
    create_cycle()

collected = gc.collect()

print "Garbage collector: collected %d objects." % (collected)
```

**输出:**

```
Garbage collector: collected 0 objects.
Creating cycles...
{1: {...}}
{2: {...}}
{3: {...}}
{4: {...}}
{5: {...}}
{6: {...}}
{7: {...}}
{8: {...}}
{9: {...}}
{10: {...}}
Garbage collector: collected 10 objects.
```

执行手动垃圾收集有两种方式:基于时间的垃圾收集和基于事件的垃圾收集。

1.  **基于时间的**垃圾收集很简单:在固定的时间间隔后调用垃圾收集器。
2.  **基于事件的**垃圾收集在事件发生时调用垃圾收集器。例如，当用户退出应用程序或应用程序进入空闲状态时。

**参考**

*   [Python 文档](https://docs.python.org/2/library/gc.html)