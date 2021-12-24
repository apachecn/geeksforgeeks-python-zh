# Python 中的数据隐藏

> 原文:[https://www.geeksforgeeks.org/data-hiding-in-python/](https://www.geeksforgeeks.org/data-hiding-in-python/)

在本文中，我们将讨论 python 中的数据隐藏，从一般的数据隐藏到 Python 中的数据隐藏，以及在 Python 中使用数据隐藏的优缺点。

### **什么是数据隐藏？**

数据隐藏是一个强调对用户隐藏数据或信息的概念。这是面向对象编程策略的关键方面之一。它包括数据成员、内部工作等对象细节。数据隐藏排除了对类成员的完整数据输入，并通过防止意外更改来保护对象完整性。数据隐藏还通过限制软件需求之间的相互依赖性来最小化系统复杂性，以提高健壮性。数据隐藏也称为信息隐藏。在类中，如果我们将数据成员声明为私有，这样其他类就不能访问数据成员，那么这就是一个隐藏数据的过程。

**Python 中的数据隐藏:**

Python 文档引入了数据隐藏，将用户与程序实现的一部分隔离开来。模块中的一些对象被保留在内部，用户看不到，也无法访问。程序中的模块很容易理解如何使用应用程序，但是客户端无法知道应用程序如何运行。因此，数据隐藏赋予了安全性，同时放弃了依赖性。Python 中的数据隐藏是保护应用程序中特定用户访问的技术。Python 应用于每一个技术领域，拥有用户友好的语法和庞大的库。Python 中的数据隐藏是使用 __ 双下划线前缀完成的。这使得类成员是非公共的，并且与其他类隔离。

**例:**

## 蟒 3

```
class Solution:
    __privateCounter = 0

    def sum(self):
        self.__privateCounter += 1
        print(self.__privateCounter)

count = Solution()
count.sum()
count.sum()

# Here it will show error because it unable
# to access private member
print(count.__privateCount)
```

**输出:**

```
Traceback (most recent call last):
  File "/home/db01b918da68a3747044d44675be8872.py", line 11, in <module>
    print(count.__privateCount) 
AttributeError: 'Solution' object has no attribute '__privateCount'
```

**为了纠正错误，我们可以通过类名访问私有成员:**

## python 3

```
class Solution:
    __privateCounter = 0

    def sum(self):
        self.__privateCounter += 1
        print(self.__privateCounter)

count = Solution()
count.sum()
count.sum()

# Here we have accessed the private data
# member through class name.
print(count._Solution__privateCounter)
```

**输出:**

```
1
2
2
```

### **数据隐藏的优势:**

1.  通过向公众隐藏易失性数据，它有助于防止对易失性数据的损坏或滥用。
2.  类对象与无关数据断开连接。
3.  它将对象作为面向对象程序设计的基本概念进行隔离。
4.  它提高了抵御无法访问重要数据的黑客的安全性。

### **数据隐藏的缺点:**

1.  它使程序员能够编写冗长的代码，对普通客户端隐藏重要数据。
2.  可见数据和不可见数据之间的联系使对象工作得更快，但是数据隐藏阻止了这种联系。