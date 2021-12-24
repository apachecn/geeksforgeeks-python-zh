# Python 中的导入模块

> 原文:[https://www.geeksforgeeks.org/import-module-python/](https://www.geeksforgeeks.org/import-module-python/)

python 中的导入类似于 C/C++中的#include header_file。Python 模块可以通过使用 import 导入文件/函数来访问另一个模块的代码。import 语句是调用导入机制的最常见方式，但不是唯一的方式。

**导入模块 _ 名称**
使用导入时，通过调用 __import__()函数，在本地范围内初始搜索模块。函数返回的值反映在初始代码的输出中。

## 大蟒

```
import math
print(math.pi)
```

输出:

```
3.141592653589793
```

**导入 module_name.member_name**
在上面的代码模块中，导入了 math，可以把它看作一个类，把 pi 作为它的对象来访问它的变量。
pi 的值由 __import__()返回。
pi 作为一个整体可以导入到我们的初始代码中，而不是导入整个模块。

## 大蟒

```
from math import pi

# Note that in the above example,
# we used math.pi. Here we have used
# pi directly.
print(pi)
```

输出:

```
3.141592653589793
```

**从 module_name 导入***
在上面的代码模块中，math 并没有导入，而只是 pi 已经作为变量导入了。
所有函数和常量都可以使用*导入。

## 大蟒

```
from math import *
print(pi)
print(factorial(6))
```

输出:

```
3.141592653589793
720
```

如上所述，import 使用 __import__()来搜索模块，如果没有找到，它将引发 ImportError

## 大蟒

```
import mathematics
print(mathematics.pi)
```

输出:

```
Traceback (most recent call last):
  File "C:/Users/GFG/Tuples/xxx.py", line 1, in 
    import mathematics
ImportError: No module named 'mathematics'
```

本文由 **Piyush Doorwar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。