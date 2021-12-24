# 为什么 python 最适合竞争编码？

> 原文:[https://www . geesforgeks . org/python-最适合-竞争-编码/](https://www.geeksforgeeks.org/python-best-suited-competitive-coding/)

当涉及到**产品型公司**时，他们需要优秀的编码员，并且需要通过**竞争编码**轮才能进入面试轮次。竞争性编码就是这样一个平台，它将同时测试你的思维能力和速度。

```
Who should read this?
    Any programmer who still hasn't tried python for
    Competitive Coding MUST give this article a read.
    This should clear up any doubts one has before 
    shifting to python.No matter how comfortable
 a programming language may seem to you right now
 Python is bound to feel even better.
    Python has a tendency of sticking to people
    like a bad habit !!
```

**速度**是 python 首屈一指的因素。与 C、C++、JAVA 等传统编程语言相比，需要键入的代码量急剧减少。另一个最重要的点是 python 为用户提供了各种各样的功能，包、**和库**，作为程序员智力的补充。
最终 python 最好的一点是它非常简单，我们不需要在输入、输出等琐事上浪费太多时间。这有助于把我们的注意力转移到手头的问题上。
在这里，我将列出一些我最喜欢的 python 特性，我相信这些特性会鼓励您开始尝试使用 Python 进行竞争性编码。

**1。变量独立性**
Python 不要求我们在使用变量之前声明变量及其数据类型。这也给了我们范围的灵活性，只要它在硬件的合理范围内，即不需要担心整数和长整数。类型转换在内部处理，结果完美无缺。

```
Amazing Fact !!
          For nested loops in python we can use the 
          same variable name in both inner and outer
          for-loop variables without fear of 
          inconsistent data or any errors !!
```

**2。常用功能，如排序、最小、最大、计数**、**等。**
最小/最大函数帮助我们从列表中找到最小/最大元素。排序功能允许我们对列表进行排序，**计数功能**帮助我们对列表中特定元素的出现次数进行计数。
**最好的是我们可以**放心**python 库为上面的每一个操作使用最好的算法。**例如，排序函数是一种非常特殊的排序算法，称为 **TIMSORT** ，其最坏情况下的时间复杂度为 O(n log n)，这是一种排序算法所能提供的最好的。

参考: [Python 排序算法](https://stackoverflow.com/questions/10948920/what-algorithm-does-pythons-sorted-use)

## 计算机编程语言

```
# Python code to demonstrate working of min(),
# max(), sorted() and count()
arr = [10, 76, 87, 45, 22, 87, 90, 87, 66, 84, 87]

print("Maximum = ",max(arr))
print("Minimum = ",min(arr))
print("The sorted array is = ",sorted(arr))
print('Number of occurrences of 87 is = ',arr.count(87))
```

输出:

```
('Maximum = ', 90)
('Minimum = ', 10)
('The sorted array is = ', [10, 22, 45, 66, 76, 84, 87, 87, 87, 87, 90])
('Number of occurrences of 87 is = ', 4)
```

**3。python 中的列表结合了数组和链表的优点。**
Python 列表提供了删除特定元素的独特功能，同时保持内存位置连续。**这个特性使得链表的概念无效**。就像类固醇上的链表！此外，插入可以在任何需要的位置进行。

## 计算机编程语言

```
# Python code to demonstrate list operations
arr = [00, 11, 22, 33, 44, 55, 66, 77, 88, 99]

# deletion via index position
del arr[5]
print(arr)

# deletion via specifying particular element
arr.remove(22)
print(arr)

# insertion at any arbitrary position
arr[-1] = "A random number"
print(arr)

# concept of sub-lists
k = arr[:2]
print(k)
```

输出:

```
[0, 11, 22, 33, 44, 66, 77, 88, 99]
[0, 11, 33, 44, 66, 77, 88, 99]
[0, 11, 33, 44, 66, 77, 88, 'A random number']
[0, 11]
```

**4。独特的列表操作–回溯、子列表。**
如果我们不确定列表的大小，那么我们可以使用索引位置-1 来访问最后一个元素。类似地，-2 可以用于第二个最后一个元素，以此类推。因此，我们可以回溯一个列表。此外，我们不需要指定任何特定的列表大小，因此它也可以作为动态分配数组。
可以提取列表的特定部分，而不必遍历列表，如以上示例所示。**关于列表的一个非常惊人的事实是，它们可以保存不同的数据类型。**过去列表是数据元素的同质集合的日子一去不复返了！！

*   **函数可以返回多个值。**
    一般其他编程语言的函数只能返回一个值但是**在 python 中****我们可以返回多个值！！**如下面的代码片段所示。

## 计算机编程语言

```
# Python code to demonstrate that a function
# can easily return multiple values.
def multi_return(*arr):
    k1 = arr[0]
    k2 = arr[1]
    return k1,k2

a,b = multi_return(11,22)
print(a,' ',b)

a,b = multi_return(55,66,77,88,99)
print(a,' ',b)
```

输出:

```
11   22
55   66
```

**5。一个函数的可变数量的参数。**
函数的参数可以以列表的形式传递，每次我们需要调用函数时，列表的大小可能会有所不同。在上面的例子中，我们首先用 2 个参数调用函数，然后用 5 个参数！！

*   **If else 和 for 循环更加用户友好。**
    python 的 if-else 语句允许我们在列表中搜索特定的元素，而不需要遍历整个列表并检查每个元素。
    有些编程语言对每个循环都有一个概念，这个概念与 for a 循环略有不同。它允许我们遍历一个列表，其中循环变量一个接一个地接受列表值。Python 将每个循环概念都包含在 for 循环本身中。

## 计算机编程语言

```
# Python code to demonstrate quick searching

arr = [1, 2, 3, 4, 5, 6, 7, 8, 9]

# searching made easy
if 3 in arr:
    print("YES")
else:
    print("NO")

#foreach loop
for i in arr:
    print(i,end = ' ')
```

输出:

```
YES
1 2 3 4 5 6 7 8 9 
```

*   **代码缩进。**
    Python 代码块是根据缩进来区分的。这提供了更好的代码可读性，并给我们灌输了缩进代码的好习惯。
*   **集合和词典的概念。**
    集合是一种无序的集合数据类型，它是可迭代的、可变的，并且没有重复的元素。这就像一个不允许重复元素的列表。
    字典就像一个列表，其**值**可以通过用户定义的**键**来访问，而不是传统的数字索引值。

## 计算机编程语言

```
# Python code to demonstrate use of dictionaries
# and sets.
a = {'a','b','c','d','e','a'}

# the second 'a' is dropped to avoid repetition
print(a)

dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
print("dict['Name']: ", dict['Name'])
print("dict['Age']: ", dict['Age'])
```

输出:

```
{'d', 'a', 'e', 'b', 'c'}
dict['Name']:  Zara
dict['Age']:  7
```

*   **健壮的输入语句。**
    在竞争性编码中，我们经常被要求将‘n’个以空格分隔的整数作为输入，并且最好将它们保存在列表/数组中。Python 提供了在一行代码中完成这一切的功能。！！

## 蟒蛇 3

```
# Python code to demonstrate how to take space
# separated inputs.
arr = [int(a) for a in input().strip().split(' ')]

print(arr)
```