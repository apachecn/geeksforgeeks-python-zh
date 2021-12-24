# Python–从矩阵中过滤代表字典键的不可变行

> 原文:[https://www . geeksforgeeks . org/python-filter-不可变-row-presentation-dictionary-key-from-matrix/](https://www.geeksforgeeks.org/python-filter-immutable-rows-representing-dictionary-keys-from-matrix/)

给定矩阵，提取所有具有元素的行，这些元素具有可以表示为字典关键字的所有元素，即不可变的。

> **输入** : test_list = [[4，5，[2，3，2]]，[“gfg”，1，(4，4)]，[{5:4}，3，“好”]，[True，“最佳”]
> **输出**:[[‘gfg’，1，(4，4)]，[True，‘最佳’]
> **解释**:元组中的所有元素都是不可变的。
> 
> **输入** : test_list = [[4，5，[2，3，2]]，[“gfg”，1，(4，4)，[3，2]]，[{5:4}，3，“good”]，[True，“best”]
> **输出** : [[True，‘best’]
> **解释**:元组中的所有元素都是不可变的。

**方法#1:使用 all() + isinstance()**

在这种情况下，我们检查所有元素是否属于不可变数据类型的实例，对于所有元素返回*真*的行将被过滤。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Filter Dictionary Key Possible Element rows
# Using all() + isinstance()

# initializing list
test_list = [[4, 5, [2, 3, 2]], ["gfg", 1, (4, 4)], [{5: 4}, 3, "good"], [
    True, "best"]]

# printing original list
print("The original list is : " + str(test_list))

# checking for each immutable data type
res = [row for row in test_list if all(isinstance(ele, int) or isinstance(ele, bool)
                                       or isinstance(ele, float) or isinstance(ele, tuple)
                                       or isinstance(ele, str) for ele in row)]

# printing result
print("Filtered rows : " + str(res))
```

**输出:**

> 原始列表为:[[4，5，[2，3，2]]，['gfg '，1，(4，4)]，[{5: 4}，3，' good']，[True，' best']
> 筛选行:[['gfg '，1，(4，4)]，[True，' best ']

**方法 2:使用 filter()+lambda+is instance()+all()**

在本例中，我们使用 *filter() + lambda* 函数执行过滤任务，其余所有功能均按上述方法执行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Filter Dictionary Key Possible Element rows
# Using filter() + lambda + isinstance() + all()

# initializing list
test_list = [[4, 5, [2, 3, 2]], ["gfg", 1, (4, 4)], [{5: 4}, 3, "good"], [
    True, "best"]]

# printing original list
print("The original list is : " + str(test_list))

# checking for each immutable data type
# filtering using filter()
res = list(filter(lambda row: all(isinstance(ele, int) or isinstance(ele, bool)
                                  or isinstance(ele, float) or isinstance(ele, tuple)
                                  or isinstance(ele, str) for ele in row), test_list))

# printing result
print("Filtered rows : " + str(res))
```

**输出:**

> 原始列表为:[[4，5，[2，3，2]]，['gfg '，1，(4，4)]，[{5: 4}，3，' good']，[True，' best']
> 筛选行:[['gfg '，1，(4，4)]，[True，' best ']