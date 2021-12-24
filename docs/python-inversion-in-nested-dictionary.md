# Python–嵌套字典中的反转

> 原文:[https://www . geeksforgeeks . org/python-嵌套反转词典/](https://www.geeksforgeeks.org/python-inversion-in-nested-dictionary/)

给定一个嵌套字典，执行键的反转，即最里面的嵌套变成最外面的，反之亦然。

> **输入** : test_dict = {"a" : {"b" : {}，
> "d" : {"e" : {}，
> " f ":{ " g ":{ }
> **输出**:{ ' b ':{ ' a ' } }，' e': {'d': {}，' g ':{ ' f ' } }
> **解释:**嵌套词典倒置为外词典键，即-a-vis
> 
> **输入**:test _ dict = { " a ":{ " b ":{ " c ":{ } } } }
> **输出**:{ ' c ':{ ' b ':{ ' a ':} } }
> **解释**:只要一个键，映射反转到深度。

**方法:使用循环+递归**

这是执行这项任务的粗暴方式。在这种情况下，我们使用递归为每个键提取从外部到内部的所有路径，然后使用它来反转结果中的顺序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Inversion in nested dictionary
# Using loop + recursion

# utility function to get all paths till end 
def extract_path(test_dict, path_way):
    if not test_dict:
        return [path_way]
    temp = []
    for key in test_dict:
        temp.extend(extract_path(test_dict[key], path_way + [key]))
    return temp

# function to compute inversion
def hlper_fnc(test_dict):
    all_paths = extract_path(test_dict, [])
    res = {}
    for path in all_paths:
        front = res
        for ele in path[::-1]:
            if ele not in front :
                front[ele] = {}
            front = front[ele]
    return res

# initializing dictionary
test_dict = {"a" : {"b" : {"c" : {}}},
             "d" : {"e" : {}},
             "f" : {"g" : {"h" : {}}}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# calling helper function for task 
res = hlper_fnc(test_dict)

# printing result 
print("The inverted dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'a': {'b': {'c': {}}}, 'd': {'e': {}}, 'f': {'g': {'h': {}}}}
The inverted dictionary : {'c': {'b': {'a': {}}}, 'e': {'d': {}}, 'h': {'g': {'f': {}}}}

```