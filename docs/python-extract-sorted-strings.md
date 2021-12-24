# Python–提取排序字符串

> 原文:[https://www . geesforgeks . org/python-extract-sorted-strings/](https://www.geeksforgeeks.org/python-extract-sorted-strings/)

给定一个字符串列表，提取所有排序的字符串。

> **输入** : test_list = [“提示”、“极客”、“鳍”、“Gfg”]
> **输出** : [“提示”、“鳍”、“Gfg”]
> **解释**:提取字符递增顺序的字符串。
> 
> **输入** : test_list = [“提示”、“极客”、“Gfg”]
> **输出** : [“提示”、“Gfg”]
> **解释**:提取字符递增顺序的字符串。

**方法#1:使用列表理解+排序()**

在本例中，我们使用 *sorted()* 执行字符串排序和比较任务，列表理解用于遍历字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract sorted strings
# Using list comprehension + sorted()

# initializing list
test_list = ["hint", "geeks", "fins", "Gfg"]

# printing original list
print("The original list is : " + str(test_list))

# sorted(), converts to sorted version and compares with
# original string
res = [sub for sub in test_list if ''.join(sorted(sub)) == sub]

# printing result
print("Sorted Strings : " + str(res))
```

**Output**

```
The original list is : ['hint', 'geeks', 'fins', 'Gfg']
Sorted Strings : ['hint', 'fins', 'Gfg']

```

**方法 2:使用 filter()+lambda+sorted()+join()**

在本例中，我们使用 *filter() + lambda* 进行过滤，使用 *join()* 将最终排序后的字符列表结果转换为字符串进行比较。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract sorted strings
# Using filter() + lambda + sorted() + join()

# initializing list
test_list = ["hint", "geeks", "fins", "Gfg"]

# printing original list
print("The original list is : " + str(test_list))

# sorted(), converts to sorted version and compares with 
# original string
res = list(filter(lambda sub : ''.join(sorted(sub)) == sub, test_list))

# printing result 
print("Sorted Strings : " + str(res))
```

**Output**

```
The original list is : ['hint', 'geeks', 'fins', 'Gfg']
Sorted Strings : ['hint', 'fins', 'Gfg']

```