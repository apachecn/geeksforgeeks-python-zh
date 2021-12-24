# 使用 Python 中的字典计算列表中的频率

> 原文:[https://www . geeksforgeeks . org/使用 python 字典计算列表中的频率/](https://www.geeksforgeeks.org/counting-the-frequencies-in-a-list-using-dictionary-in-python/)

给定一些元素的未排序列表(可能是整数，也可能不是整数)，使用字典查找列表中每个不同元素的频率。
**例:**

```
Input : [1, 1, 1, 5, 5, 3, 1, 3, 3, 1,
                  4, 4, 4, 2, 2, 2, 2]
Output : 1 : 5
         2 : 4
         3 : 3
         4 : 3
         5 : 2
Explanation : Here 1 occurs 5 times, 2 
              occurs 4 times and so on...
```

这个问题可以用许多方法解决。一种简单的方法是遍历列表，将列表中每个不同的元素用作字典的关键字，并将该关键字的相应计数存储为值。下面是这种方法的 Python 代码:

## 计算机编程语言

```
# Python program to count the frequency of
# elements in a list using a dictionary

def CountFrequency(my_list):

    # Creating an empty dictionary
    freq = {}
    for item in my_list:
        if (item in freq):
            freq[item] += 1
        else:
            freq[item] = 1

    for key, value in freq.items():
        print ("% d : % d"%(key, value))

# Driver function
if __name__ == "__main__":
    my_list =[1, 1, 1, 5, 5, 3, 1, 3, 3, 1, 4, 4, 4, 2, 2, 2, 2]

    CountFrequency(my_list)
```

**Output:** 

```
 1 :  5
 2 :  4
 3 :  3
 4 :  3
 5 :  2
```

**时间复杂度:** O(N)，其中 N 为列表长度。

**替代方法:**一种替代方法可以是使用 list.count()方法。

## 计算机编程语言

```
# Python program to count the frequency of
# elements in a list using a dictionary

def CountFrequency(my_list):

    # Creating an empty dictionary
    freq = {}
    for items in my_list:
        freq[items] = my_list.count(items)

    for key, value in freq.items():
        print ("% d : % d"%(key, value))

# Driver function
if __name__ == "__main__":
    my_list =[1, 1, 1, 5, 5, 3, 1, 3, 3, 1, 4, 4, 4, 2, 2, 2, 2]
    CountFrequency(my_list)
```

**Output:** 

```
 1 :  5
 2 :  4
 3 :  3
 4 :  3
 5 :  2
```

**时间复杂度:** O(N <sup>2</sup> ，其中 N 为列表长度。时间复杂度 list.count()单独为 O(N)，在循环内使用时会变成 O(N <sup>2</sup> )。

**替代方法:**一种替代方法可以是使用 dict.get()方法。这使得程序更加简短，并且使得理解 get 方法是如何有用的，而不是 if…else。

## 计算机编程语言

```
# Python program to count the frequency of
# elements in a list using a dictionary

def CountFrequency(my_list):

   # Creating an empty dictionary
   count = {}
   for i in [1, 1, 1, 5, 5, 3, 1, 3, 3, 1 ,4, 4, 4, 2, 2, 2, 2]:
    count[i] = count.get(i, 0) + 1
   return count

# Driver function
if __name__ == "__main__":
    my_list =[1, 1, 1, 5, 5, 3, 1, 3, 3, 1, 4, 4, 4, 2, 2, 2, 2]
    print(CountFrequency(my_list))
```

**Output:** 

```
{1: 5, 5: 2, 3: 3, 4: 3, 2: 4}
```

**相关文章:**
[使用集合模块](https://www.geeksforgeeks.org/count-frequencies-elements-array-python-using-collections-module/)
统计 Python 中数组中所有元素的频率