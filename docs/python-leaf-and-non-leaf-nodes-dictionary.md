# Python–叶子和非叶子节点字典

> 原文:[https://www . geesforgeks . org/python-叶子和非叶子节点-字典/](https://www.geeksforgeeks.org/python-leaf-and-non-leaf-nodes-dictionary/)

有时，在使用 Python 时，我们会遇到一个问题，即我们需要处理以字典形式表示的图形数据。在这种情况下，我们可能需要检查所有叶节点和非前导节点。这类问题在机器学习算法中有直接的应用。让我们讨论一下执行这项任务的方法。

> **输入** : test_dict = {'Gfg': {'is': 2，' best': 1}}
> **输出** : { '叶':2，'非叶':1}
> **输入**:test _ dict = { ' Gfg ':{ ' best ':2 } }
> **输出** : { '非叶':1，'叶':1}

**方法:使用递归+ isinstance() + loop**
以上功能的组合可以用来解决这个问题。在本文中，我们使用递归来重现内部嵌套，并使用 isinstance()通过值类型来检查叶或非叶。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Leaf and Non-Leaf Nodes Dictionary
# Using recursion + isinstance() + loop

def hlpr_fnc(dict1, res = {'non-leaf':0, 'leaf':0}):

    #res['non-leaf'] += 1  
    nodes = dict1.keys()
    for node in nodes:
      subnode = dict1[node]
      if isinstance(subnode, dict):
        res['non-leaf'] += 1
        hlpr_fnc(subnode, res)
      else:
        res['leaf'] += 1 
    return res

# initializing dictionary
test_dict = {'a': {'b': 1, 'c': {'d': {'e': 2, 'f': 1}}, 'g': {'h': {'i': 2, 'j': 1}}}}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Leaf and Non-Leaf Nodes Dictionary
# Using recursion + isinstance() + loop
res = hlpr_fnc(test_dict)

# printing result
print("The leaf and Non-Leaf nodes : " + str(res))
```

**输出:**

```
The original dictionary : {'a': {'b': 1, 'c': {'d': {'e': 2, 'f': 1}}, 'g': {'h': {'i': 2, 'j': 1}}}}
The leaf and Non-Leaf nodes : {'non-leaf': 5, 'leaf': 5}
```