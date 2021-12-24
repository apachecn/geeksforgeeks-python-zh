# Python 中的循环技术

> 原文:[https://www.geeksforgeeks.org/looping-techniques-python/](https://www.geeksforgeeks.org/looping-techniques-python/)

Python 在各种顺序容器中通过某些内置函数支持各种循环技术。这些方法主要在竞争性编程中非常有用，在需要特定技术的各种项目中也非常有用，循环保持了代码的整体结构。节省了大量的时间和内存空间，因为不需要声明我们在传统循环方法中声明的额外变量。

**它们用在哪里？**
不同的循环技术主要用于我们不需要实际操作整个容器的结构和顺序的地方，而是只打印单次使用实例的元素，容器中不会发生原地更改。这也可以在实例中使用，以节省时间。

**使用 Python 数据结构的不同循环技术有:**

*   **使用 enumerate():** enumerate()用于在容器中循环打印索引号以及该特定索引中的值。

## 蟒蛇 3

```py
# python code to demonstrate working of enumerate()

for key, value in enumerate(['The', 'Big', 'Bang', 'Theory']):
    print(key, value)
```

**输出:**

```py
0 The
1 Big
2 Bang
3 Theory
```

## 蟒蛇 3

```py
# python code to demonstrate working of enumerate()

for key, value in enumerate(['Geeks', 'for', 'Geeks', 'is', 'the', 'Best', 'Coding', 'Platform']):
    print(value, end=' ')
```

**输出:**

```py
Geeks for Geeks is the Best Coding Platform 
```

*   **使用 zip():** zip()用于组合两个相似的容器(list-list 或 dict-dict)按顺序打印值。循环只存在到较小的容器结束。关于 zip()和 enumerate()的详细解释可以在[这里](https://www.geeksforgeeks.org/using-iterations-in-python-effectively/)找到。

## 蟒蛇 3

```py
# python code to demonstrate working of zip()

# initializing list
questions = ['name', 'colour', 'shape']
answers = ['apple', 'red', 'a circle']

# using zip() to combine two containers
# and print values
for question, answer in zip(questions, answers):
    print('What is your {0}?  I am {1}.'.format(question, answer))
```

**输出:**

```py
What is your name?  I am apple.
What is your color?  I am red.
What is your shape?  I am a circle.
```

*   **使用 ITER item():**ITER item()用于循环遍历字典，顺序打印字典键值对。
*   **使用 items():** items()在字典上执行与 item()类似的任务，但与 item()相比有一定的缺点。
    *   是**非常耗时的**。在大型字典中调用它会消耗大量时间。
    *   这需要很大的内存。有时候查字典需要双倍的记忆。

**例 1:**

## 蟒蛇 3

```py
# python code to demonstrate working of iteritems(),items()

d = { "geeks" : "for", "only" : "geeks" }

# using iteritems to print the dictionary key-value pair
print ("The key value pair using iteritems is : ")
for i,j in d.items():
    print( i,j )

# using items to print the dictionary key-value pair
print ("The key value pair using items is : ")
for i,j in d.items():
    print( i,j )
```

**输出:**

```py
The key value pair using iteritems is : 
geeks for
only geeks
The key value pair using items is : 
geeks for
only geeks
```

**例 2:**

## 蟒蛇 3

```py
# python code to demonstrate working of items()

king = {'Akbar': 'The Great', 'Chandragupta': 'The Maurya',
        'Modi' : 'The Changer'}

# using items to print the dictionary key-value pair
for key, value in king.items():
    print(key, value)
```

**输出:**

```py
Akbar The Great
Chandragupta The Maurya
Modi The Changer
```

*   **使用 sorted():** sorted()用于打印**容器的排序顺序**。它**不会对容器**进行排序，而只是按照排序顺序打印容器 1 个实例。使用 **set()可以组合删除重复的**事件。

**例 1:**

## 蟒蛇 3

```py
# python code to demonstrate working of sorted()

# initializing list
lis = [ 1 , 3, 5, 6, 2, 1, 3 ]

# using sorted() to print the list in sorted order
print ("The list in sorted order is : ")
for i in sorted(lis) :
    print (i,end=" ")

print ("\r")

# using sorted() and set() to print the list in sorted order
# use of set() removes duplicates.
print ("The list in sorted order (without duplicates) is : ")
for i in sorted(set(lis)) :
    print (i,end=" ")
```

**输出:**

```py
The list in sorted order is : 
1 1 2 3 3 5 6 
The list in sorted order (without duplicates) is : 
1 2 3 5 6 
```

**例 2:**

## 蟒蛇 3

```py
# python code to demonstrate working of sorted()

# initializing list
basket = ['guave', 'orange', 'apple', 'pear',
          'guava', 'banana', 'grape']

# using sorted() and set() to print the list
#  in sorted order
for fruit in sorted(set(basket)):
    print(fruit)
```

**输出:**

```py
apple
banana
grape
guava
guave
orange
pear
```

*   **使用 reversed():** reversed()用于以相反的顺序打印****容器的值。它不反映对原始列表
    的任何更改****

****例 1:****

## **蟒蛇 3**

```py
# python code to demonstrate working of reversed()

# initializing list
lis = [ 1 , 3, 5, 6, 2, 1, 3 ]

# using revered() to print the list in reversed order
print ("The list in reversed order is : ")
for i in reversed(lis) :
    print (i,end=" ")
```

****输出:****

```py
The list in reversed order is : 
3 1 2 6 5 3 1 
```

****例 2:****

## **蟒蛇 3**

```py
# python code to demonstrate working of reversed()

# using reversed() to print in reverse order
for i in reversed(range(1, 10, 3)):
    print (i)
```

****输出:****

```py
7
4
1
```

*   **这些技术使用起来很快，减少了编码工作。因为，while 循环需要更改容器的整个结构。**
*   **这些循环技术不需要对容器进行任何结构更改。它们有表达使用目的的关键词。然而，不能预先预测或猜测，而循环，即不容易一目了然的目的。**
*   **循环技术使代码比使用 for & while 循环更简洁。**