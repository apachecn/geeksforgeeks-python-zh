# 函子及其在 Python 中的使用

> 原文:[https://www.geeksforgeeks.org/functors-use-python/](https://www.geeksforgeeks.org/functors-use-python/)

让我们先来理解函子:
函子是可以被当作函数来对待的对象。

**什么时候用函子？**

*   当您想要隐藏/抽象真实实现时，可以使用函子。假设您希望根据输入调用不同的函数，但不希望用户代码对这些不同的函数进行显式调用。这是函子可以帮助的理想情况。
*   在这个场景中，我们可以寻找一个函子，它根据输入在内部调用最合适的函数
*   现在，如果以后调用的函数都没有增加，那么这将只是后端代码中的一个简单更改，而不会干扰任何用户代码。因此，函子有助于创建可维护、解耦和可扩展的代码。

让我们通过一个简单的设计问题例子来理解它。问题是设计类/方法，根据输入类型调用不同的排序方法。如果输入是 int 类型，那么应该调用 Mergesort 函数，如果输入是 float 类型，那么就调用 Heapsort，否则就调用 quicksort 函数

```
# Python code to illustrate program 
# without functors 
class GodClass(object): 

    def DoSomething(self,x): 

        x_first=x[0] 

        if type(x_first) is int : 
            return self.__MergeSort(x) 
        if type(x_first) is float : 
            return self.__HeapSort(x) 
        else : 
            return self.__QuickSort(x) 

    def __MergeSort(self,a): 
        #" Dummy MergeSort " 
        print ("Data is Merge sorted")
        return a 

    def __HeapSort(self,b): 
        # " Dummy HeapSort " 
        print( "Data is Heap sorted")
        return b

    def __QuickSort(self,c): 
        # "Dummy QuickSort" 
        print ("Data is Quick sorted")
        return c 
# Here the user code need to know about the conditions for calling different strategy 
# and making it tightly coupled code. 

godObject=GodClass() 
print (godObject.DoSomething([1,2,3])) 
```

输出:

```
Data is Merge sorted
[1, 2, 3]

```

**本规范**
1 中有一些明显的设计空白。内部实现应该对用户代码隐藏，即应该维护抽象
2。每个类都应该处理单一的职责/功能。
2。代码是紧密耦合的。

让我们用 python 中的函子来解决同样的问题

```
# Python code to illustrate program 
# using functors 

class Functor(object): 
    def __init__(self, n=10): 
        self.n = n 

    # This construct allows objects to be called as functions in python 
    def __call__(self, x) : 
        x_first = x[0] 
        if type(x_first) is int: 
            return self. __MergeSort(x) 
        if type(x_first) is float: 
            return self. __HeapSort(x) 
        else : 
            return self.__QuickSort(x) 

    def __MergeSort(self,a): 
        #" Dummy MergeSort " 
        print ("Data is Merge sorted")
        return a 
    def __HeapSort(self,b): 
        # " Dummy HeapSort " 
        print ("Data is Heap sorted")
        return b 
    def __QuickSort(self,c): 
        # "Dummy QuickSort" 
        print ("Data is Quick sorted")
        return c 

# Now let's code the class which will call the above functions. 
# Without the functor this class should know which specific function to be called 
# based on the type of input 

### USER CODE 
class Caller(object): 
    def __init__(self): 
        self.sort=Functor() 

    def Dosomething(self,x): 
# Here it simply calls the function and doesn't need to care about 
# which sorting is used. It only knows that sorted output will be the 
# result of this call 
        return self.sort(x) 

Call=Caller() 

# Here passing different input 
print(Call.Dosomething([5,4,6])) # Mergesort 

print(Call.Dosomething([2.23,3.45,5.65])) # heapsort 
print(Call.Dosomething(['a','s','b','q'])) # quick sort 
# creating word vocab 
```

输出:

```

Data is Merge sorted
[5, 4, 6]
Data is Heap sorted
[2.23, 3.45, 5.65]
Data is Quick sorted
['a', 's', 'b', 'q']

```

上述设计使得在不干扰任何用户代码的情况下改变底层策略或实现变得容易。用户代码可以可靠地使用上面的函子，而不知道引擎盖下发生了什么，
使代码解耦，易于扩展和维护。

现在，除了 python 中的函数，您也已经理解了 Python 中的策略模式，该模式要求调用特定函数的类和列出或选择策略的类之间的分离。

参考文献:
[https://www . daniweb . com/programming/software-development/threads/485098/python 中的函子](https://www.daniweb.com/programming/software-development/threads/485098/functors-in-python)

本文由**安基特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。