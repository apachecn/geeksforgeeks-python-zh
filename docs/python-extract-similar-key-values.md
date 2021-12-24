# Python–提取相似键值

> 原文:[https://www . geesforgeks . org/python-extract-相似-键值/](https://www.geeksforgeeks.org/python-extract-similar-key-values/)

给定一个字典，提取所有来自相似关键字的值，即包含所有相似的字符，只是相互混杂形成。

> **输入** : test_dict = {'gfg' : 5，' ggf' : 19，' gffg' : 9，' gff' : 3，' fgg' : 3}，tst_wrd = 'fgg'
> **输出**:【5，19，3】
> **解释** : gfg，ggf，fgg 有值，5，19，3。
> 
> **输入** : test_dict = {'gfg' : 5，' gffg' : 9，' gff' : 3，' fgg' : 3}，tst_wrd = 'fgg'
> **输出**:【5，3】
> **解释** : gfg 和 fgg 有值，5 和 3。

**方法#1:使用排序的()+循环**

在这种情况下，我们将排序后的关键字与目标关键字进行比较，将具有正确顺序的相似元素，并且可以检查是否相等。一旦匹配，就提取它们的值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract Similar Key Values
# Using loop + sorted()

# initializing dictionary
test_dict = {'gfg': 5, 'ggf': 19, 'gffg': 9, 'gff': 3, 'fgg': 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing word
tst_wrd = 'fgg'

res = []
for key, val in test_dict.items():

    # sorted to get similar key order
    if ''.join(list(sorted(key))) == tst_wrd:
        res.append(val)

# printing result
print("The extracted keys : " + str(res))
```

**输出:**

> 原始字典为:{'gfg': 5，' ggf': 19，' gffg': 9，' gff': 3，' fgg': 3}
> 提取的键:[5，19，3]

**方法 2:使用列表理解+排序()**

在这种情况下，我们执行与上面类似的任务，只是使用速记使用 *sorted()* 和列表理解来执行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract Similar Key Values
# Using list comprehension + sorted()

# initializing dictionary
test_dict = {'gfg': 5, 'ggf': 19, 'gffg': 9, 'gff': 3, 'fgg': 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing word
tst_wrd = 'fgg'

# one-liner to solve this
res = [val for key, val in test_dict.items(
) if ''.join(list(sorted(key))) == tst_wrd]

# printing result
print("The extracted keys : " + str(res))
```

**输出:**

> 原始字典为:{'gfg': 5，' ggf': 19，' gffg': 9，' gff': 3，' fgg': 3}
> 提取的键:[5，19，3]