# Python–独特的扁平化词典

> 原文:[https://www . geesforgeks . org/python-distinct-flat-dictionary/](https://www.geeksforgeeks.org/python-distinct-flatten-dictionaries/)

有时候，在使用字典的时候，我们可以有一些键，这些键本身就是非常复杂的嵌套的一部分，我们希望将特定键嵌套的所有键和值提取到一个单独的列表中。这种问题在很多领域都有应用，比如 web 开发。让我们讨论执行这项任务的某些方法。
**方法#1:使用 loop + isinstance() +列表理解**
以上功能的组合可以用来解决这个问题。在本文中，我们使用带有 isinstance()和 loop 的检查来执行展平字典的任务。最后利用列表理解以字典列表的形式编译结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Distinct Flatten dictionaries
# Using loop + isinstance() + list comprehension

def flatten(temp_dict, temp_list):
    for key, val in temp_dict.items():
        if isinstance(val, dict):
            temp_list.append(key)
            flatten(val, temp_list)
        else:
            temp_list.extend([key, val])
    return temp_list

# initializing dictionary
test_dict = {'gfg' : {'is' : 4, "best" : 10}, 'is' : {'for' : { 'geeks' : 8 }}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Distinct Flatten dictionaries
# Using loop + isinstance() + list comprehension
res = [flatten(val, [key]) for key, val in test_dict.items()]

# printing result 
print("The flattened dictionary elements : " + str(res)) 
```

**Output : **

```
The original dictionary is : {'is': {'for': {'geeks': 8}}, 'gfg': {'is': 4, 'best': 10}} 
The flattened dictionary elements : [['is', 'for', 'geeks', 8], ['gfg', 'is', 4, 'best', 10]]  
```

**方法 2:使用 yield + isinstance()**
该任务也可以使用上述功能的组合来执行。在这种情况下，我们使用使用 yield 的动态数据渲染来使过程紧凑和可读。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Distinct Flatten dictionaries
# Using yield + isinstance()

def flatten(temp_dict):
    if isinstance(temp_dict, dict):
        for key, val in temp_dict.items():
            yield key
            yield from flatten(val)
    else:
        yield temp_dict

# initializing dictionary
test_dict = {'gfg' : {'is' : 4, "best" : 10}, 'is' : {'for' : { 'geeks' : 8 }}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Distinct Flatten dictionaries
# Using yield + isinstance()
res = [[key, *flatten(val)] for key, val in test_dict.items()]

# printing result 
print("The flattened dictionary elements : " + str(res)) 
```

**Output : **

```
The original dictionary is : {'is': {'for': {'geeks': 8}}, 'gfg': {'is': 4, 'best': 10}} 
The flattened dictionary elements : [['is', 'for', 'geeks', 8], ['gfg', 'is', 4, 'best', 10]]  
```