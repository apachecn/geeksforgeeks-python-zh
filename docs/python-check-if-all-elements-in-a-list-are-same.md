# Python |检查列表中的所有元素是否相同

> 原文:[https://www . geesforgeks . org/python-检查列表中的所有元素是否相同/](https://www.geeksforgeeks.org/python-check-if-all-elements-in-a-list-are-same/)

给定一个列表，编写一个 Python 程序来检查给定列表中的所有元素是否相同。

**示例:**

```
Input: ['Geeks', 'Geeks', 'Geeks', 'Geeks', ]
Output: Yes

Input: ['Geeks', 'Is', 'all', 'Same', ]
Output: No
```

我们有各种方法可以完成这项任务。让我们用不同的方法来检查列表中的所有元素是否相同。

**方法#1:** 比较各元素。

```
# Python program to check if all 
# ments in a List are same 

def ckeckList(lst):

    ele = lst[0]
    chk = True

    # Comparing each element with first item 
    for item in lst:
        if ele != item:
            chk = False
            break;

    if (chk == True): print("Equal")
    else: print("Not equal")            

# Driver Code
lst = ['Geeks', 'Geeks', 'Geeks', 'Geeks', ]
ckeckList(lst)
```

**输出:**

```
Equal
```

但是在 Python 中，我们可以用非常有趣的方式完成同样的任务。

**方法#2:** 使用 all()方法

```
# Python program to check if all 
# elements in a List are same 
res = False

def chkList(lst):
    if len(lst) < 0 :
        res = True
    res = all(ele == lst[0] for ele in lst)

    if(res):
        print("Equal")
    else:
        print("Not equal")

# Driver Code        
lst = ['Geeks', 'Geeks', 'Geeks', 'Geeks']
chkList(lst)
```

**输出:**

```
Equal
```

**方法#3:** 使用 count()方法

```
# Python program to check if all 
# elements in a List are same 
res = False

def chkList(lst):
    if len(lst) < 0 :
        res = True
    res = lst.count(lst[0]) == len(lst)

    if(res):
        print("Equal")
    else:
        print("Not equal")

# Driver Code        
lst = ['Geeks', 'Geeks', 'Geeks', 'Geeks']
chkList(lst)
```

**输出:**

```
Equal
```

**方法#4:** 使用集合数据结构
由于我们知道集合中不能有重复的元素，所以我们可以使用这个属性来检查所有元素是否相同。

```
# Python program to check if all 
# elements in a List are same 

def chkList(lst):
    return len(set(lst)) == 1

# Driver Code        
lst = ['Geeks', 'Geeks', 'Geeks', 'Geeks']

if chkList(lst) == True: print("Equal")
else: print("Not Equal")
```

**输出:**

```
Equal
```