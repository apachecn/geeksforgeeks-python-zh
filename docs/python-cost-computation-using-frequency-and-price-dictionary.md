# Python–使用频率和价格字典计算成本

> 原文:[https://www . geesforgeks . org/python-成本-计算-使用频率和价格-字典/](https://www.geeksforgeeks.org/python-cost-computation-using-frequency-and-price-dictionary/)

给定价格和频率字典，计算产品的总成本，即通过对每个项目的价格和频率的乘积求和。

> **输入** : test_dict = {“苹果”:2、“芒果”:2、“葡萄”:2}、{“苹果”:2、“芒果”:2、“葡萄”:2}
> **输出** : 12
> **解释** : (2*2) + (2*2) + (2*2) = 12。
> 
> **输入** : test_dict = {“苹果”:3、“芒果”:2、“葡萄”:3}、{“苹果”:2、“芒果”:2、“葡萄”:2}
> **输出** : 16
> **解释**:积的求和得出 16 如上。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，我们遍历所有的键，并将每个元素的频率乘以其成本，并继续执行中间求和。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Cost computation using Frequency and Price dictionary
# Using loop

# initializing dictionary
test_dict = {"Apple" : 5, "Mango" : 8, "Grapes" : 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing Frequency dict 
cost_dict = {"Apple" : 3, "Mango" : 4, "Grapes" : 6}

res = 0
for key in test_dict:

    # computing summation of product
    res = res + (test_dict[key] * cost_dict[key])

# printing result 
print("The extracted summation : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Apple': 5, 'Mango': 8, 'Grapes': 10}
The extracted summation : 107

```

**方法 2:使用 sum() +列表理解**

这些功能的结合为解决这个问题提供了一种捷径。在本文中，我们使用 sum()执行求和，并使用列表理解来编译结果和迭代。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Cost computation using Frequency and Price dictionary
# Using sum() + list comprehension

# initializing dictionary
test_dict = {"Apple" : 5, "Mango" : 8, "Grapes" : 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing Frequency dict 
cost_dict = {"Apple" : 3, "Mango" : 4, "Grapes" : 6}

# using list comprehension and sum() to provide one-liner
res = sum([cost_dict[key] * test_dict[key] for key in test_dict])

# printing result 
print("The extracted summation : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Apple': 5, 'Mango': 8, 'Grapes': 10}
The extracted summation : 107

```