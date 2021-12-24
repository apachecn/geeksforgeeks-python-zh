# Python |组合列表字典中的值

> 原文:[https://www . geesforgeks . org/python-组合值-来自列表词典/](https://www.geeksforgeeks.org/python-combining-values-from-dictionary-of-list/)

给定一个列表值的字典，任务是在每个组合中组合每个键值对。

> **输入:**
> {“名称”:[“Paras”、“Chunky”]，
> “站点”:[“geeks forgeeks”、“Cyware”、“Google”]}
> 
> **输出:**
> 【{ ' Site ':' Geeksforgeeks '，' Name': 'Paras'}，{'Site': 'Cyware '，' Name': 'Paras'}，
> {'Site': 'Google '，' Name ':' Site ':' Geeksforgeeks '，' Name': 'Chunky'}，
> {'Site': 'Cyware '，' Name': 'Chunky'}，{'Site': 'Google '，' Name': 'Chunky'}]

**方法#1:使用 itertools 并排序**

```
# Python code to combine every key value
# pair in every combinations

# List initialization
Input = {
"Bool" : ["True", "False"],
"Data" : ["Int", "Float", "Long Long"],
}

# Importing
import itertools as it

# Sorting input
sorted_Input = sorted(Input)

# Using product after sorting
Output = [dict(zip(sorted_Input, prod)) 
          for prod in it.product(*(Input[sorted_Input]
          for sorted_Input in sorted_Input))]

# Printing output
print(Output)
```

**Output:**

> [{'Bool'： 'True'， 'Data'： 'Int'}， {'Bool'： 'True'， 'Data'： 'Float'}， {'Bool'： 'True'， 'Data'： 'Long Long Long'}， {'Bool'： 'False'， 'Data'： 'Int'}， {'Bool'： 'False'， 'Data'： 'Float'}， {'Bool'： 'False'， 'Data'： 'Long Long'}]

**方法 2:使用 Zip**

```
# Python code to combine every key value
# pair in every combinations

# Importing
import itertools

# Input Initialization
Input = {
"Bool" : ["True", "False"],
"Data" : ["Int", "Float", "Long Long"],
}

# using zip and product without sorting
Output = [[{key: value} for (key, value) in zip(Input, values)] 
              for values in itertools.product(*Input.values())]

# Printing output
print(Output)
```

**Output:**

> [[{'Data'： 'Int'}， {'Bool'： 'True'}]， [{'Data'： 'Int'}， {'Bool'： 'False'}]， [{'Data'： 'Float'}， {'Bool'： 'True'}]， [{'Data'： 'Float'}， {'Bool'： 'False'}]， [{'Data'： 'Long Long'}]