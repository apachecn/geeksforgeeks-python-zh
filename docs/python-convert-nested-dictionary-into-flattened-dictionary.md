# Python |将嵌套词典转换为扁平词典

> 原文:[https://www . geesforgeks . org/python-convert-nested-dictionary-in-flatted-dictionary/](https://www.geeksforgeeks.org/python-convert-nested-dictionary-into-flattened-dictionary/)

给定一个嵌套字典，任务是将该字典转换成一个扁平字典，在嵌套键启动的情况下，键用' _ '分隔。

下面给出了几个解决上述任务的方法。

**方法#1:使用天真方法**

## 蟒蛇 3

```py
# Python code to demonstrate
# conversion of nested dictionary
# into flattened dictionary

# code to convert ini_dict to flattened dictionary
# default separator '_'
def flatten_dict(dd, separator ='_', prefix =''):
    return { prefix + separator + k if prefix else k : v
             for kk, vv in dd.items()
             for k, v in flatten_dict(vv, separator, kk).items()
             } if isinstance(dd, dict) else { prefix : dd }

# initialising_dictionary
ini_dict = {'geeks': {'Geeks': {'for': 7}},
            'for': {'geeks': {'Geeks': 3}},
            'Geeks': {'for': {'for': 1, 'geeks': 4}}}

# printing initial dictionary
print ("initial_dictionary", str(ini_dict))

# printing final dictionary
print ("final_dictionary", str(flatten_dict(ini_dict)))
```

**Output:** initial_dictionary {‘geeks’: {‘Geeks’: {‘for’: 7}}, ‘Geeks’: {‘for’: {‘geeks’: 4, ‘for’: 1}}, ‘for’: {‘geeks’: {‘Geeks’: 3}}} final_dictionary {‘Geeks_for_for’: 1, ‘geeks_Geeks_for’: 7, ‘for_geeks_Geeks’: 3, ‘Geeks_for_geeks’: 4}  

**方法 2:使用** ***相互解决问题***

## 蟒蛇 3

```py
# Python code to demonstrate
# conversion of nested dictionary
# into flattened dictionary

from collections import MutableMapping

# code to convert ini_dict to flattened dictionary
# default separator '_'
def convert_flatten(d, parent_key ='', sep ='_'):
    items = []
    for k, v in d.items():
        new_key = parent_key + sep + k if parent_key else k

        if isinstance(v, MutableMapping):
            items.extend(convert_flatten(v, new_key, sep = sep).items())
        else:
            items.append((new_key, v))
    return dict(items)

# initialising_dictionary
ini_dict = {'geeks': {'Geeks': {'for': 7}},
            'for': {'geeks': {'Geeks': 3}},
            'Geeks': {'for': {'for': 1, 'geeks': 4}}}

# printing initial dictionary
print ("initial_dictionary", str(ini_dict))

# printing final dictionary
print ("final_dictionary", str(convert_flatten(ini_dict)))
```

**Output:** initial_dictionary {‘Geeks’: {‘for’: {‘for’: 1, ‘geeks’: 4}}, ‘for’: {‘geeks’: {‘Geeks’: 3}}, ‘geeks’: {‘Geeks’: {‘for’: 7}}} final_dictionary {‘Geeks_for_geeks’: 4, ‘for_geeks_Geeks’: 3, ‘geeks_Geeks_for’: 7, ‘Geeks_for_for’: 1}  

**方法三:使用 Python** ***生成器***

## 蟒蛇 3

```py
# Python code to demonstrate
# conversion of nested dictionary
# into flattened dictionary

my_map = {"a" : 1,
        "b" : {
            "c": 2,
            "d": 3,
            "e": {
                "f":4,
                6:"a",
                5:{"g" : 6},
                "l":[1,"two"]
            }
        }}

# Expected Output
# {'a': 1, 'b_c': 2, 'b_d': 3, 'b_e_f': 4, 'b_e_6': 'a', 'b_e_5_g': 6, 'b_e_l': [1, 'two']}

ini_dict = {'geeks': {'Geeks': {'for': 7}},
            'for': {'geeks': {'Geeks': 3}},
            'Geeks': {'for': {'for': 1, 'geeks': 4}}}

# Expected Output
# {‘Geeks_for_geeks’: 4, ‘for_geeks_Geeks’: 3, ‘Geeks_for_for’: 1, ‘geeks_Geeks_for’: 7}

def flatten_dict(pyobj, keystring=''):
    if type(pyobj) == dict:
        keystring = keystring + '_' if keystring else keystring
        for k in pyobj:
            yield from flatten_dict(pyobj[k], keystring + str(k))
    else:
        yield keystring, pyobj

print("Input : %s\nOutput : %s\n\n" %
     (my_map, { k:v for k,v in flatten_dict(my_map) }))

print("Input : %s\nOutput : %s\n\n" %
     (ini_dict, { k:v for k,v in flatten_dict(ini_dict) }))
```

**Output:** initial_dictionary {‘for’: {‘geeks’: {‘Geeks’: 3}}, ‘geeks’: {‘Geeks’: {‘for’: 7}}, ‘Geeks’: {‘for’: {‘for’: 1, ‘geeks’: 4}}} final_dictionary {‘Geeks_for_geeks’: 4, ‘for_geeks_Geeks’: 3, ‘Geeks_for_for’: 1, ‘geeks_Geeks_for’: 7}