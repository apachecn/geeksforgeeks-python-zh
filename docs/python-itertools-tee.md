# python–te tools . tee()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-tertools-tee/

在 Python 中，Itertools 是内置的模块，允许我们以有效的方式处理迭代器。它们使得遍历像列表和字符串这样的数据项变得非常容易。一个这样的 itertools 函数是 **filterfalse()。**

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

## 三通()功能

这个迭代器将容器分成参数中提到的多个迭代器。

**语法:**

```py
tee(iterator, count)
```

**参数:**这个方法包含两个参数，第一个参数是迭代器，第二个参数是整数。
**返回值:**这个方法返回参数中提到的迭代器个数。

**例 1:**

```py
# Python code to demonstrate the working of tee() 

# importing "itertools" for iterator operations 
import itertools 

# initializing list  
li = [2, 4, 6, 7, 8, 10, 20] 

# storing list in iterator 
iti = iter(li) 

# using tee() to make a list of iterators 
# makes list of 3 iterators having same values. 
it = itertools.tee(iti, 3) 

# printing the values of iterators 
print ("The iterators are : ") 
for i in range (0, 3): 
    print (list(it[i])) 
```

**输出:**

```py
The iterators are : 
[2, 4, 6, 7, 8, 10, 20]
[2, 4, 6, 7, 8, 10, 20]
[2, 4, 6, 7, 8, 10, 20]

```

**例 2:**

```py
# Python code to demonstrate the working of tee() 

# importing "itertools" for iterator operations 
import itertools

# using tee() to make a list of iterators 

iterator1, iterator2 = itertools.tee([1, 2, 3, 4, 5, 6, 7], 2)

# printing the values of iterators 
print (list(iterator1)) 
print (list(iterator1)) 
print (list(iterator2)) 
```

**输出:**

```py
[1, 2, 3, 4, 5, 6, 7]
[]
[1, 2, 3, 4, 5, 6, 7]

```

**例 3:**

```py
# Python code to demonstrate the working of tee() 

# importing "itertools" for iterator operations 
import itertools

# using tee() to make a list of iterators 

for i in itertools.tee(['a', 'b', 'c', 'd', 'e', 'f', 'g'], 4):
    # printing the values of iterators 
    print (list(i))
```

**输出:**

```py
['a', 'b', 'c', 'd', 'e', 'f', 'g']
['a', 'b', 'c', 'd', 'e', 'f', 'g']
['a', 'b', 'c', 'd', 'e', 'f', 'g']
['a', 'b', 'c', 'd', 'e', 'f', 'g']

```