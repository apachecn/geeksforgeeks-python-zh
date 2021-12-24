# Python–提取字符串列表中以 K 开头的单词

> 原文:[https://www . geesforgeks . org/python-extract-words-以-k 开头的字符串列表/](https://www.geeksforgeeks.org/python-extract-words-starting-with-k-in-string-list/)

给定短语列表，提取所有以字符 k 开头的字符串

> **输入**:test _ list =【“Gfg 好学习”“Gfg 好极客”“我爱 G4G”】，K = l
> **输出**:【‘学习’，‘爱情’】
> **解释**:提取所有以 L 为起始字母的元素。
> 
> **输入**:test _ list =【“Gfg 好学”“Gfg 是极客”“我爱 G4G”】，K = m
> **输出**:【
> **解释**:没有从“m”开始的单词，因此没有提取单词。

**方法#1:使用循环+拆分()**

这是解决这个问题的粗暴方法。在这种情况下，我们将每个短语转换成单词列表，然后检查每个单词的初始字符是否为 k。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract words starting with K in String List
# Using loop + split()

# initializing list
test_list = ["Gfg is best", "Gfg is for geeks", "I love G4G"] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = "g"

res = []
for sub in test_list:
    # splitting phrases
    temp = sub.split()
    for ele in temp:

        # checking for matching elements
        if ele[0].lower() == K.lower():
            res.append(ele)

# printing result 
print("The filtered elements : " + str(res))
```

**Output**

```
The original list is : ['Gfg is best', 'Gfg is for geeks', 'I love G4G']
The filtered elements : ['Gfg', 'Gfg', 'geeks', 'G4G']

```

**方法 2:使用列表理解+拆分()**

这是执行这项任务的另一种方式。在本文中，我们在单个列表理解中运行双重嵌套循环，并执行必要的条件检查。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract words starting with K in String List
# Using list comprehension + split() 

# initializing list
test_list = ["Gfg is best", "Gfg is for geeks", "I love G4G"] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = "g"
res = [ele for temp in test_list for ele in temp.split() if ele[0].lower() == K.lower()]

# printing result 
print("The filtered elements : " + str(res))
```

**Output**

```
The original list is : ['Gfg is best', 'Gfg is for geeks', 'I love G4G']
The filtered elements : ['Gfg', 'Gfg', 'geeks', 'G4G']

```