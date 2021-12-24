# 如何从 Python 调用 C / C++呢？

> 原文:[https://www.geeksforgeeks.org/how-to-call-c-c-from-python/](https://www.geeksforgeeks.org/how-to-call-c-c-from-python/)

为了利用这两种语言的优势，开发人员使用 python 绑定，这允许他们从 Python 调用 C/C++库。

现在，问题出现了，为什么有必要这样做？

1.  我们知道，C 有更快的执行速度，为了克服 python 中全局解释器锁(GIL)的限制，python 绑定很有帮助。
2.  我们有一个大的、稳定的、经过测试的 C/C++库，使用起来会很方便。
3.  使用 Python 测试工具对系统进行大规模测试。

让我们看看我们想用 Python 执行的 C 代码:

## C++

```py
#include <iostream>
class Geek{
    public:
        void myFunction(){
            std::cout << "Hello Geek!!!" << std::endl;
        }
};
int main()
{
    // Creating an object
    Geek t; 

    // Calling function
    t.myFunction();  

    return 0;
}
```

我们必须将这些 cpp 声明作为外部“C”提供，因为 ctypes 只能与 C 函数交互。

## C++

```py
extern "C" {
    Geek* Geek_new(){ return new Geek(); }
    void Geek_myFunction(Geek* geek){ geek -> myFunction(); }
}
```

现在，将这段代码编译到共享库中:

![](img/3150bacb8c8eb7b7063214a73f5b5e2a.png)

最后，编写 python 包装器:

## 蟒蛇 3

```py
# import the module
from ctypes import cdll

# load the library
lib = cdll.LoadLibrary('./libgeek.so')

# create a Geek class
class Geek(object):

    # constructor
    def __init__(self):

        # attribute
        self.obj = lib.Geek_new()

    # define method
    def myFunction(self):
        lib.Geek_myFunction(self.obj)

# create a Geek class object
f = Geek()

# object method calling
f.myFunction()
```

**输出:**

```py
Hello Geek!!!

```