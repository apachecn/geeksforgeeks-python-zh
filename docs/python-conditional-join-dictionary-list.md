# Python–条件连接字典列表

> 原文:[https://www . geesforgeks . org/python-条件-连接-字典-列表/](https://www.geeksforgeeks.org/python-conditional-join-dictionary-list/)

给定两个字典列表，任务是编写一个 Python 程序，根据相似索引字典中特定键的相似性来执行条件连接，即添加键。

**示例:**

> **输入:**test _ list 1 =[{“gfg”:1，“is”:3，“best”:2 }，{“gfg”:1，“best”:6 }，{“all”:7，“best”:10 }]，
> 
> test_list2 = [{“好”:4，“最好”:2}，{“极客”:2，“最好”:3 }，{“CS”:2，“最好”:10 } ]，test_key =“最好”
> 
> **输出:** [{'gfg': 1，' is': 3，' best': 2，' good': 4}，{'gfg': 1，' best': 6}，{'all': 7，' best': 10，' CS': 2}]
> 
> **说明:** best 在第 0 个索引的两个字典中都有 2，因此在索引 0 处，字典被合并。
> 
> **输入:**test _ list 1 =[{“gfg”:1，“is”:3，“best”:3 }，{“gfg”:1，“best”:6 }，{“all”:7，“best”:10 }]，
> 
> test_list2 = [{“好”:4，“最好”:2}，{“极客”:2，“最好”:3 }，{“CS”:2，“最好”:10 } ]，test_key =“最好”
> 
> **输出:** [{'gfg': 1，' is': 3，' best': 3}，{'gfg': 1，' best': 6}，{'all': 7，' best': 10，' CS': 2}]
> 
> **说明:** best 在第二索引的两个字典中都有 10，因此在索引 2 处，字典被合并。

**方法:使用**[**next()**](https://www.geeksforgeeks.org/python-next-method/)**+**[**更新()**](https://www.geeksforgeeks.org/python-dictionary-update-method/)

在这种情况下，我们使用生成器表达式来检查字典的键是否与相似的索引字典键匹配，如果匹配，则使用 update()合并所有对应的键。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Conditional Join Dictionary List
# Using update() + next()

# initializing lists
test_list1 = [{"gfg": 1, "is": 3, "best": 2}, {
    "gfg": 1, "best": 6}, {"all": 7, "best": 10}]
test_list2 = [{"good": 4, "best": 2}, {
    "geeks": 2, "best": 3},  {"CS": 2, "best": 10}]

# printing original list
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# initializing test key
test_key = "best"

for sub1 in test_list1:

    # checking for matching key
    temp = next(
        (itm for itm in test_list2 if sub1[test_key] == itm[test_key]), None)
    if(temp):

        # performing update
        sub1.update(temp)

# printing result
print("Joined result : " + str(test_list1))
```

**输出:**

> 原始列表 1 是:[{'gfg': 1，' is': 3，' best': 2}，{'gfg': 1，' best': 6}，{'all': 7，' best': 10}]
> 
> 原始列表 2 是:[{ '好':4，'最好':2}，{ '极客':2，'最好':3}，{'CS': 2，'最好':10}]
> 
> 联接结果:[{'gfg': 1，' is': 3，' best': 2，' good': 4}，{'gfg': 1，' best': 6}，{'all': 7，
> 
> 最佳:10，“CS”:2 }]