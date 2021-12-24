# Python–字典值列表

中第 k 个索引处具有最大元素的键

> 原文:[https://www . geesforgeks . org/python-key-with-max-element-at-kth-index-in-dictionary-value-list/](https://www.geeksforgeeks.org/python-key-with-maximum-element-at-kth-index-in-dictionary-value-list/)

给定一个以值为列表的字典，任务是编写一个 Python 程序，通过比较每个列表的元素来获取第 K<sup>索引处元素最大的键。</sup>

> **输入** : test_dict = {'Gfg' : [4，6，8，2]，
> 'is' : [1，4，5，9]，
> 'best' :[2，3，4，10]，
> 'for' :[4，5，2，1]，
> 'geeks' :[2，10，1，8]}，K = 3
> **输出** : best
> **解释** : 2，2
> 
> **输入** : test_dict = {'Gfg' : [4，6，8，2]，
> 'is' : [1，4，5，9]，
> 'best' :[2，3，4，10]，
> 'for' :[4，5，2，1]，
> 'geeks' :[2，10，1，8]}，K = 2
> **输出**:Gfg
> T10】解释 : 8

**方法一:** *使用* [*排序()，*](https://www.geeksforgeeks.org/sorted-function-python/) [*字典理解*](https://www.geeksforgeeks.org/python-dictionary-comprehension/) *和*[T19】λT21】](https://www.geeksforgeeks.org/python-lambda/)

在这种情况下，我们对索引 K 值处的所有列表元素及其键执行反向排序，然后输出提取的最大值的键。

**示例:**

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Key with Maximum element at Kth index 
# in Dictionary Value List Using sorted()
# + dictionary comprehension + lambda

# initializing dictionary
test_dict = {'Gfg': [4, 6],
             'is': [1, 4, 5, 9, 4, 5, 7],
             'best': [2, 3, 4, 10],
             'for': [4],
             'geeks': [2, 10, 1, 10]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K
K = 3

# sorted sorting all the values in reverse order
# Maximum element is found at 1st position
temp = sorted({key: val[K] if K <= len(val) else -1 for key,
               val in test_dict.items()}.items(),
              key=lambda sub: sub[1], reverse=True)

# getting all maximum keys in case of multiple
res = []
for idx, ele in enumerate(temp):
    res.append(temp[idx][0])
    if temp[idx][1] != temp[idx + 1][1]:
        break

# printing result
print("The extracted key : " + str(res))
```

**输出:**

> 原词典为:{'Gfg': [4，6，8，2，5，6]，' is': [1]，' best': [2，3，4，10]，' for': [4，5，2，1]，' geeks': [2，10，1，10]}
> 
> 提取的关键字:[“最佳”、“极客”

**方法二:** *使用* [*max()*](https://www.geeksforgeeks.org/max-min-python/) *和* [*发生器表达式*](https://www.geeksforgeeks.org/generator-expressions/)

在本例中，我们使用 max()执行获取最大值的任务，生成器表达式用于迭代字典中的所有键。下一步，我们得到所有匹配 k 处最大元素的键。

**示例:**

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Key with Maximum element at Kth index 
# in Dictionary Value List Using max()
# + generator expression

# initializing dictionary
test_dict = {'Gfg': [4, 6, 8, 2, 5, 6],
             'is': [1],
             'best': [2, 3, 4, 10],
             'for': [4, 5, 2, 1],
             'geeks': [2, 10, 1, 10]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K
K = 3

# sorted sorting all the values in reverse order
# Maximum element is found at 1st position
# getting maximum
temp = max(test_dict[key][K] if K < len(
    test_dict[key]) else -1 for key in test_dict)

# getting all keys with maximum.
res = []
for key in test_dict:
    if K < len(test_dict[key]) and test_dict[key][K] == temp:
        res.append(key)

# printing result
print("The extracted key : " + str(res))
```

**输出:**

> 原词典为:{'Gfg': [4，6，8，2，5，6]，' is': [1]，' best': [2，3，4，10]，' for': [4，5，2，1]，' geeks': [2，10，1，10]}
> 
> 提取的关键字:[“最佳”、“极客”