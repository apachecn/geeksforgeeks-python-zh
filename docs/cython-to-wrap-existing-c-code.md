# Cython 包装现有 C 代码

> 原文:[https://www . geesforgeks . org/cyt hon-to-wrap-existing-c-code/](https://www.geeksforgeeks.org/cython-to-wrap-existing-c-code/)

**什么是 Cython？**
它是 Python 编程语言和扩展的 Cython 编程语言的优化静态编译器。它用于使为 Python 编写 C 扩展变得像 Python 本身一样容易。

它提供了许多**有用的特性**:

*   编写在 C/C++代码之间来回调用的 Python 代码。
*   通过添加静态类型声明，轻松地将可读的 Python 代码调整为普通的 C 语言性能。
*   使用组合源代码级调试来查找给定 Python、Cython 和 C 代码中的错误。
*   与大型数据集的高效交互，例如使用多维 NumPy 数组。
*   与来自低级或高性能库和应用程序的现有代码和数据集成。

与 Cython 进行扩展是一项棘手的任务。为此，需要创建包装函数的集合。假设显示的工作代码已经编译成名为 ***libwork*** 的 C 库。下面的代码将创建一个名为`**csample.pxd**`的文件。

**代码#1 :**

```
# cwork.pxd
#
# Declarations of "external" C 
# functions and structures

cdef extern from "work.h":

    int gcd(int, int)
    int divide(int, int, int *)
    double avg(double *, int) nogil

    ctypedef struct Point:
        double x
        double y

    double distance(Point *, Point *)
```

在 Cython 中，上面的代码将作为一个 C 头文件工作。来自`"work.h"`的初始声明 *cdef extern* 声明所需的 C 头文件。接下来的声明取自标题。这个文件的名字是`**cwork.pxd**`。下一个目标是创建一个`**work.pyx**`文件，该文件将定义将 Python 解释器连接到`cwork.pxd`文件中声明的底层 C 代码的包装器。

**代码#2 :**

```
# work.pyx
# Import the low-level C declarations

cimport cwork
# Importing functionalities from Python
# and the C stdlib
from cpython.pycapsule cimport * 
from libc.stdlib cimport malloc, free

# Wrappers
def gcd(unsigned int x, unsigned int y):
    return cwork.gcd(x, y)

def divide(x, y):
    cdef int rem
    quot = cwork.divide(x, y, &rem)
    return quot, rem

def avg(double[:] a):
    cdef:
        int sz
        double result

    sz = a.size

    with nogil:
        result = cwork.avg(<double *> &a[0], sz)

    return result
```

**代码#3 :**

```
# Destructor for cleaning up Point objects
cdef del_Point(object obj):
    pt = <csample.Point *> PyCapsule_GetPointer(obj, "Point")
    free(<void *> pt)

# Create a Point object and return as a capsule
def Point(double x, double y):
    cdef csample.Point * p
    p = <csample.Point *> malloc(sizeof(csample.Point))

    if p == NULL:
        raise MemoryError("No memory to make a Point")

    p.x = x
    p.y = y

    return PyCapsule_New(<void *>p, "Point",
                         <PyCapsule_Destructor>del_Point)

def distance(p1, p2):
    pt1 = <csample.Point *> PyCapsule_GetPointer(p1, "Point")
    pt2 = <csample.Point *> PyCapsule_GetPointer(p2, "Point")

    return csample.distance(pt1, pt2)
```

最后，构建扩展模块，创建`**work.py**`文件。

**代码#4:**

```
# importing libraries
from distutils.core import setup
from distutils.extension import Extension
from Cython.Distutils import build_ext

ext_modules = [Extension('work', 
                         ['work.pyx'], 
                         libraries=['work'], 
                         library_dirs=['.'])]

setup(name = 'work extension module',
      cmdclass = {'build_ext': build_ext},
      ext_modules = ext_modules)
```

**代码#5:构建用于实验的结果模块。**

```
bash % python3 setup.py build_ext --inplace
running build_ext

cythoning work.pyx to work.c
building 'work' extension

gcc -fno-strict-aliasing -DNDEBUG -g -fwrapv -O3 -Wall -Wstrict-prototypes
-I/usr/local/include/python3.3m -c work.c
-o build/temp.macosx-10.6-x86_64-3.3/work.o

gcc -bundle -undefined dynamic_lookup build/temp.macosx-10.6-x86_64-3.3/work.o
-L. -lwork -o work.so
bash %
```

现在，我们有了一个扩展模块`**work.so**`。让我们看看它是如何工作的。

**代码#6 :**

```
import sample
print ("GCD : ", sample.gcd(12, 8))

print ("\nDivision : ", sample.divide(42,10))

import array
arr = array.array('d',[1,2,3])
print ("\nAverage  : ", sample.avg(a)

pt1 = sample.Point(2,3)
pt2 = sample.Point(4,5)

print ("\npt1 : ", pt1)
print ("\npt2 : ", pt2)

print ("\nDistance between the two points : ", 
       sample.distance(pt1, pt2))
```

**输出:**

```
GCD : 4

Division : (4, 2)

Average : 2.0

pt1 : <capsule object "Point" at 0x1005d1e70>

pt2 : <capsule object "Point" at 0x1005d1ea0>

Distance between the two points : 2.8284271247461903

```

在高水平上，使用 Cython 是模仿 c .*T5。pxd* 文件只包含 C 定义(类似于`.h`文件)，而`**.pyx**`文件包含实现(类似于`.c`文件)。Cython 使用 **cimport** 语句从`**.pxd**`文件导入定义。这不同于使用普通的 Python 导入语句，后者会加载普通的 Python 模块。