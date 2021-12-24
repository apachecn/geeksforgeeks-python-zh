# Python–如果字符串长度等于 K，则过滤字符串元组

> 原文:[https://www . geesforgeks . org/python-filter-string-元组-if-string-length-equals-k/](https://www.geeksforgeeks.org/python-filter-string-tuples-if-string-lengths-equals-k/)

给定元组列表，过滤元组，其元素字符串长度等于 k

> **输入**:test _ list =[(“ABC”、“Gfg”、“CS1”)、(“Gfg”、“Best”)、(“Gfg”、“WoOW”)]，K = 3
> **输出**:[(“ABC”、“Gfg”、“CS1”)]
> **:以上元组中所有字符串长度均为 3。**
> 
> ****输入**:test _ list =[(“ABCD”、“Gfg”、“CS1”)、(“Gfg”、“Best”)、(“Gfg”、“WoOW”)]，K = 3
> **输出** : []
> **解释**:以上元组中没有长度为 3 的字符串。**

****方法#1:使用循环****

**在这种情况下，我们运行嵌套循环来测试每个字符串，如果等于 K，那么元组被附加到结果列表，否则它被省略。**

## **蟒蛇 3**

```
# Python3 code to demonstrate working of 
# Filter String Tuples if String lengths equals K
# Using loop

# initializing list
test_list = [("ABC", "Gfg", "CS1"), ("Gfg", "Best"), ("Gfg", "WoW")]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

res_list = []
for sub in test_list:
    res = True 
    for ele in sub:

        # check using len() the lengths
        if len(ele) != K :
            res = False 
            break
    if res:
        res_list.append(sub)

# printing result 
print("The filtered tuples : " + str(res_list))
```

****Output**

```
The original list is : [('ABC', 'Gfg', 'CS1'), ('Gfg', 'Best'), ('Gfg', 'WoW')]
The filtered tuples : [('ABC', 'Gfg', 'CS1'), ('Gfg', 'WoW')]

```** 

****方法 2:使用 all() +列表理解****

**压缩方式，使用 all()检查长度等价性，并使用列表理解进行迭代。**

## **蟒蛇 3**

```
# Python3 code to demonstrate working of 
# Filter String Tuples if String lengths equals K
# Using all() + list comprehension

# initializing list
test_list = [("ABC", "Gfg", "CS1"), ("Gfg", "Best"), ("Gfg", "WoW")]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

# all checks for all lengths equals K 
res = [sub for sub in test_list if all(len(ele) == K for ele in sub)]

# printing result 
print("The filtered tuples : " + str(res))
```

****Output**

```
The original list is : [('ABC', 'Gfg', 'CS1'), ('Gfg', 'Best'), ('Gfg', 'WoW')]
The filtered tuples : [('ABC', 'Gfg', 'CS1'), ('Gfg', 'WoW')]

```**