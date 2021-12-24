# copyreg —注册泡菜支持功能

> 原文:[https://www . geeksforgeeks . org/copy reg-register-pickle-support-functions/](https://www.geeksforgeeks.org/copyreg-register-pickle-support-functions/)

copyreg 模块定义了在酸洗或复制时酸洗特定对象所使用的功能。这个模块提供关于不是类的对象构造函数(可能是工厂函数或类实例)的配置信息。

**copy reg . constructor(object)**
该函数用于声明对象为有效的构造函数。如果一个对象不可调用，那么它就不被认为是有效的构造函数。如果对象不可调用，此函数将引发类型错误。

**copyreg.pickle(类型，函数，构造函数=无)**
这用于将函数声明为类型对象的“约简”函数。函数应该返回包含两个或三个元素的字符串或元组。
构造函数参数可选。它是一个可调用的对象，当在酸洗时用函数返回的参数元组调用时，它可以用来重构对象。如果对象是类或构造函数不可调用，则会引发类型错误。

**示例:**

```
# Python 3 program to illustrate 
# use of copyreg module 
import copyreg, copy, pickle 

class B(object): 
    def __init__(self, a): 
        self.a = a 

def pickle_b(b): 
    print("pickling a C instance...") 
    return C, (b.a, ) 

copyreg.pickle(B, pickle_b) 
b = B(1) 
d = copy.copy(b) 
print (d) 

r = pickle.dumps(b) 
print (r) 
```

**输出:**

```
pickling a C instance...

pickling a C instance...
b'\x80\x03c__main__\nC\nq\x00K\x01\x85q\x01Rq\x02.'

```

本文由**阿迪提·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。