# 将多个 JSON 文件转换为 CSV Python

> 原文:[https://www . geesforgeks . org/convert-multi-JSON-files-to-CSV-python/](https://www.geeksforgeeks.org/convert-multiple-json-files-to-csv-python/)

在本文中，我们将学习如何在 Python 中将多个 JSON 文件转换为 CSV 文件。在此之前，只要回忆一些术语:

*   **JSON 文件**:JSON 文件可以是以 JavaScript 对象符号(JSON)格式存储简单数据结构和对象的文件，可以是标准的数据交换格式。它主要用于在互联网应用程序和服务器之间传输数据。
*   **CSV 文件**:CSV 可以是逗号分隔值文件，允许数据以表格格式保存。CSV 看起来就像是一个普通的电子表格，但是带有一个**。CSV** 分机。CSV 文件通常用于几乎任何电子表格程序，如微软 Excel 或谷歌电子表格。

为了从多个 json 文件形成一个 CSV 文件，我们必须使用嵌套的 json 文件，展平数据帧或将 json 文件加载到 dataframe 的形式，连接/合并/连接这些文件以形成一个 dataframe(所有 JSON 文件中至少有一列应该相同)，最后将该 dataframe 转换为 CSV 文件。借助下面给出的例子，可以理解给定任务的全部过程:

**例 1:如果所有列都匹配**

在本例中，我们将加载两个 json 文件，将一个连接到另一个，并转换为 CSV 文件。用于此目的的 json 文件有:

**文件 1.json**

```py
{
    "ID":{
        "0":23,
        "1":43,
        "2":12,
        "3":13,
        "4":67,
        "5":89
        },
    "Name":{
        "0":"Ram",
        "1":"Deep",
        "2":"Yash",
        "3":"Aman",
        "4":"Arjun",
        "5":"Aditya"
        },
    "Marks":{
        "0":89,
        "1":97,
        "2":45,
        "3":78,
        "4":56,
        "5":76
        },
    "Grade":{
        "0":"B",
        "1":"A",
        "2":"F",
        "3":"C",
        "4":"E",
        "5":"C"
        }
}

```

**文件 2.json**

```py
{
    "ID":{
        "0":90,
        "1":56,
        "2":34,
        "3":96,
        "4":45
         },
    "Name":{
        "0":"Akash",
        "1":"Chalsea",
        "2":"Divya",
        "3":"Sajal",
        "4":"Shubham"
        },
    "Marks":{
        "0":81,
        "1":87,
        "2":100,
        "3":89,
        "4":78
        },
    "Grade":{
        "0":"B",
        "1":"B",
        "2":"A",
        "3":"B",
        "4":"C"
        }
}

```

**第一步:**借助熊猫数据框加载 json 文件。
**步骤 2 :** 将数据帧连接成一个数据帧。
**第三步:**将串接的数据帧转换成 CSV 文件。

结果的完整代码如下所示:

#### 代码:

## 蟒蛇 3

```py
# importing packages
import pandas as pd

# load json file using pandas
df1 = pd.read_json('file1.json')

# view data
print(df1)

# load json file using pandas
df2 = pd.read_json('file2.json')

# view data
print(df2)

# use pandas.concat method 
df = pd.concat([df1,df2])

# view the concatenated dataframe
print(df)

# convert dataframe to csv file
df.to_csv("CSV.csv",index=False)

# load the resultant csv file
result = pd.read_csv("CSV.csv")

# and view the data
print(result)
```

**输出:**

```py
   ID    Name  Marks Grade
0  23     Ram     89     B
1  43    Deep     97     A
2  12    Yash     45     F
3  13    Aman     78     C
4  67   Arjun     56     E
5  89  Aditya     76     C

   ID     Name  Marks Grade
0  90    Akash     81     B
1  56  Chalsea     87     B
2  34    Divya    100     A
3  96    Sajal     89     B
4  45  Shubham     78     C

   ID     Name  Marks Grade
0  23      Ram     89     B
1  43     Deep     97     A
2  12     Yash     45     F
3  13     Aman     78     C
4  67    Arjun     56     E
5  89   Aditya     76     C
0  90    Akash     81     B
1  56  Chalsea     87     B
2  34    Divya    100     A
3  96    Sajal     89     B
4  45  Shubham     78     C

    ID     Name  Marks Grade
0   23      Ram     89     B
1   43     Deep     97     A
2   12     Yash     45     F
3   13     Aman     78     C
4   67    Arjun     56     E
5   89   Aditya     76     C
6   90    Akash     81     B
7   56  Chalsea     87     B
8   34    Divya    100     A
9   96    Sajal     89     B
10  45  Shubham     78     C

```

**例 2:如果某些列匹配**

在这个例子中，我们将加载两个 json 文件，合并它们并转换成一个 CSV 文件。用于此目的的 json 文件有:

**文件 3.json**

```py
{
    "ID":{
        "0":23,
        "1":43,
        "2":12,
        "3":13,
        "4":67,
        "5":89
        },
    "Name":{
        "0":"Ram",
        "1":"Deep",
        "2":"Yash",
        "3":"Aman",
        "4":"Arjun",
        "5":"Aditya"
        },
    "Marks":{
        "0":89,
        "1":97,
        "2":45,
        "3":78,
        "4":56,
        "5":76
        }
}

```

**文件 4.json**

```py
{
    "ID":{
        "0":23,
        "1":43,
        "2":12,
        "3":67,
        "4":89
        },
    "Name":{
        "0":"Ram",
        "1":"Deep",
        "2":"Yash",
        "3":"Arjun",
        "4":"Aditya"
        },
    "Grade":{
        "0":"B",
        "1":"A",
        "2":"F",
        "3":"E",
        "4":"C"
        }
}

```

**第一步:**借助熊猫数据框加载 json 文件。

**步骤 2:** 通过不同的方法将数据帧合并为内/外/左/右连接。

**步骤 3:** 将合并后的数据帧转换为 CSV 文件。

结果的完整代码如下所示:

**代码:**

## 蟒蛇 3

```py
# importing packages
import pandas as pd

# load json file using pandas
df1 = pd.read_json('file3.json')

# view data
print(df1)

# load json file using pandas
df2 = pd.read_json('file4.json')

# view data
print(df2)

# use pandas.merge method
df_inner = pd.merge(df1, df2, how='inner', left_on=[
                    'ID', 'Name'], right_on=['ID', 'Name'])
df_outer = pd.merge(df1, df2, how='outer', left_on=[
                    'ID', 'Name'], right_on=['ID', 'Name'])
df_left = pd.merge(df1, df2, how='left', left_on=[
                   'ID', 'Name'], right_on=['ID', 'Name'])
df_right = pd.merge(df1, df2, how='right', left_on=[
                    'ID', 'Name'], right_on=['ID', 'Name'])

# convert dataframe to csv file
df_inner.to_csv("CSV_inner.csv", index=False)
df_outer.to_csv("CSV_outer.csv", index=False)
df_left.to_csv("CSV_left.csv", index=False)
df_right.to_csv("CSV_right.csv", index=False)

# load the resultant csv file
result_inner = pd.read_csv("CSV_inner.csv")
result_outer = pd.read_csv("CSV_outer.csv")
result_left = pd.read_csv("CSV_left.csv")
result_right = pd.read_csv("CSV_right.csv")

# and view the data
print(result_outer)
print(result_inner)
print(result_left)
print(result_right)
```

**输出:**

```py
   ID    Name  Marks
0  23     Ram     89
1  43    Deep     97
2  12    Yash     45
3  13    Aman     78
4  67   Arjun     56
5  89  Aditya     76

   ID    Name Grade
0  23     Ram     B
1  43    Deep     A
2  12    Yash     F
3  67   Arjun     E
4  89  Aditya     C

   ID    Name  Marks Grade
0  23     Ram     89     B
1  43    Deep     97     A
2  12    Yash     45     F
3  13    Aman     78   NaN
4  67   Arjun     56     E
5  89  Aditya     76     C

   ID    Name  Marks Grade
0  23     Ram     89     B
1  43    Deep     97     A
2  12    Yash     45     F
3  67   Arjun     56     E
4  89  Aditya     76     C

   ID    Name  Marks Grade
0  23     Ram     89     B
1  43    Deep     97     A
2  12    Yash     45     F
3  13    Aman     78   NaN
4  67   Arjun     56     E
5  89  Aditya     76     C

   ID    Name  Marks Grade
0  23     Ram     89     B
1  43    Deep     97     A
2  12    Yash     45     F
3  67   Arjun     56     E
4  89  Aditya     76     C

```

**例 3:如果给出嵌套 json 文件**

在这个例子中，我们将加载嵌套的 json 文件，将其展平，然后转换为 CSV 文件。用于此目的的 json 文件是:

**文件 5.json**

```py
{
  "tickets":[
    {
      "Name": "Liam",
      "Location": {
        "City": "Los Angeles",
        "State": "CA"
      },
      "hobbies": [
        "Piano",
        "Sports"
      ],
      "year" : 1985,
      "teamId" : "ATL",
      "playerId" : "barkele01",
      "salary" : 870000
    },
    {
      "Name": "John",
      "Location": {
        "City": "Los Angeles",
        "State": "CA"
      },
      "hobbies": [
        "Music",
        "Running"
      ],
      "year" : 1985,
      "teamId" : "ATL",
      "playerId" : "bedrost01",
      "salary" : 550000
    }
  ],
  "count": 2
}

```

**第一步:**借助 json.load()方法加载嵌套的 json 文件。

**步骤 2:** 使用 pandas 方法展平不同的列值。

**步骤 3:** 将展平的数据帧转换为 CSV 文件。

对两个嵌套文件重复上述步骤，然后按照示例 1 或示例 2 进行转换。要转换单个嵌套的 json 文件，请遵循下面给出的方法。

结果的完整代码如下所示:

**代码:**

## 蟒蛇 3

```py
# importing packages
import pandas as pd
import json

# load json file using json.load
with open('file5.json') as file:
    data = json.load(file)

# view data
print(data)

# form the dataframe
df = pd.DataFrame(data['tickets'])

# view dataframe
print(df)

# flattern the dataframe and remove unnecessary columns
for i, item in enumerate(df['Location']):
    df['location_city'] = dict(df['Location'])[i]['City']
    df['location_state'] = dict(df['Location'])[i]['State']

for i, item in enumerate(df['hobbies']):
    df['hobbies_{}'.format(i)] = dict(df['hobbies'])[i]

df = df.drop({'Location', 'hobbies'}, axis=1)

# view dataframe
print(df)

# convert dataframe to csv file
df.to_csv("CSV.csv", index=False)

# load the resultant csv file
result = pd.read_csv("CSV.csv")

# and view the data
print(result)
```