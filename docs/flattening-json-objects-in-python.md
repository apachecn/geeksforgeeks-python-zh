# 在 Python 中展平 JSON 对象

> 原文:[https://www . geesforgeks . org/扁平化-json-objects-in-python/](https://www.geeksforgeeks.org/flattening-json-objects-in-python/)

[JSON(JavaScript 对象符号)](https://www.geeksforgeeks.org/javascript-json/)是一种人类可读文本的数据交换格式，用于传输数据，尤其是在网络应用程序和服务器之间。JSON 文件就像 Python 中的嵌套字典。要将一个文本文件转换成 JSON，Python 中有一个`json`模块。该模块内置 Python 标准模块，无需外接安装。

扁平化 json 什么都不是，但是不存在嵌套，只存在键值对。

**示例:**

> **unfetened JSON:**
> {【用户】:{【瑞秋】:{【UserID】:1717171717，
> 【Email】:【Rachel 1999 @ Gmail . com】，
> 【好友】:【【约翰】、【杰里米】、【艾米丽】】}}
> 
> **扁平化 JSON:**
> { ' user _ Rachel _ friends _ 2 ':' Emily '，' user_Rachel_friends_0': 'John '，' user_Rachel_UserID': 1717171717，' user _ Rachel _ Email ':' Rachel 1999 @ Gmail . com '，' user _ Rachel _ friends _ 1 ':' Jeremy ' }

#### 需要扁平化 JSON

需要展平 JSON 的原因有很多，比如为了一个更好、更容易理解的视图，即只存在键值对，没有任何嵌套。它还允许以可读但更详细的方式实现特定于上下文的安全性和约束。

#### 一种扁平化 JSON 的方法

有很多方法可以展平 JSON。使用`json-flatten`库有一种递归方式和另一种递归方式。

*   **Recursive Approach: Now we can flatten the dictionary array by a recursive approach which is quite easy to understand. The recursive approach is a bit slower than using `json-flatten` library.

    **示例:**

    ```
    # for a array value of a key
    unflat_json = {'user' :
                   {'Rachel':
                    {'UserID':1717171717,
                    'Email': 'rachel1999@gmail.com', 
                    'friends': ['John', 'Jeremy', 'Emily']
                    }
                   }
                  }

    # Function for flattening 
    # json
    def flatten_json(y):
        out = {}

        def flatten(x, name =''):

            # If the Nested key-value 
            # pair is of dict type
            if type(x) is dict:

                for a in x:
                    flatten(x[a], name + a + '_')

            # If the Nested key-value
            # pair is of list type
            elif type(x) is list:

                i = 0

                for a in x:                
                    flatten(a, name + str(i) + '_')
                    i += 1
            else:
                out[name[:-1]] = x

        flatten(y)
        return out

    # Driver code
    print(flatten_json(unflat_json))
    ```

    **输出:**

    > { ' user _ Rachel _ friends _ 2 ':' Emily '，' user_Rachel_friends_0': 'John '，' user_Rachel_UserID': 1717171717，' user _ Rachel _ Email ':' Rachel 1999 @ Gmail . com '，' user _ Rachel _ friends _ 1 ':' Jeremy ' }** *   ****Using flatten_json library: json-flatten library provides functions for flattening a JSON object to a single key-value pairs, and unflattening that dictionary back to a JSON object.

    **安装库**

    为了使用 flatten _ json 库，我们需要安装这个库。可以通过在终端中运行以下命令来安装 flatten _ json。

    ```
    pip install json-flatten
    ```

    **示例:**

    ```
    from flatten_json import flatten

    unflat_json = {'user' :
                   {'Rachel':
                    {'UserID':1717171717,
                    'Email': 'rachel1999@gmail.com', 
                    'friends': ['John', 'Jeremy', 'Emily']
                    }
                   }
                  }

    flat_json = flatten(unflat_json)

    print(flat_json)
    ```

    **输出:**

    > {'user_Rachel_UserID': 17171717，' user _ Rachel _ Email ':' Rachel 1999 @ Gmail . com '，' user_Rachel_friends_0': 'John '，' user_Rachel_friends_1': 'Jeremy '，' user _ Rachel _ friends _ 2 ':' Emily ' }****