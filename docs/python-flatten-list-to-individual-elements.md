# Python–将列表展平为单个元素

> 原文:[https://www . geeksforgeeks . org/python-将列表展平为单个元素/](https://www.geeksforgeeks.org/python-flatten-list-to-individual-elements/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，需要对列表执行展平，即将混合列表转换为展平列表。这可以在使用 1D 列表作为输入的域中应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+ `isinstance()`**
上述功能的组合可用于执行该任务。在这种情况下，我们会检查列表的实例，并将其展平，然后粗暴地添加其他元素到列表中。

```py
# Python3 code to demonstrate 
# Flatten List to individual elements
# using loop + isinstance()

def flatten(test_list):
    if isinstance(test_list, list):
        temp = []
        for ele in test_list:
            temp.extend(flatten(ele))
        return temp
    else:
        return [test_list]

# Initializing list
test_list = ['gfg', 1, [5, 6, 'geeks'], 67.4, [5], 'best']

# printing original list
print("The original list is : " + str(test_list))

# Flatten List to individual elements
# using loop + isinstance()
res = flatten(test_list)

# printing result 
print ("The List after flattening : " + str(res))
```

**Output :**

> 原列表为:['gfg '，1，[5，6，'极客']，67.4，[5]，' best']
> 扁平化后的列表:['gfg '，1，5，6，'极客'，67.4，5，' best']