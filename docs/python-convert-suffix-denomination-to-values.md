# Python–将后缀面额转换为数值

> 原文:[https://www . geesforgeks . org/python-convert-后缀-面额-值/](https://www.geeksforgeeks.org/python-convert-suffix-denomination-to-values/)

给定带面额后缀的字符串列表，任务是编写 Python 程序将字符串转换为其实际值，替代面额实际值。

> **输入**:test _ list =[“25Cr”、“7M”、“24B”、“9L”、“2Tr”、“17K”]
> **输出**:【2500000000.0、7000000.0、2400000000.0、900000.0、20000000000.0、17000.0】
> **解释**:后缀替换
> 
> **输入**:test _ list =【“25Cr”、“7M”、“24B”】
> **输出**:【2500000000.0、7000000.0、240000000.0】
> **解释**:后缀按符号符号替换为数字。

**进场:使用** [**飘()**](https://www.geeksforgeeks.org/float-in-python/) **+** [**字典**](https://www.geeksforgeeks.org/python-dictionary/) **+** [**循环**](https://www.geeksforgeeks.org/python-for-loops/)

在这种情况下，我们用原始值构建一个所有面额的字典，然后将该值转换为浮点值，并与面额的实际值相乘。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Suffix denomination to Values
# Using float() + dictionary + loop

# initializing list
test_list = ["25Cr", "7M", "24B", "9L", "2Tr", "17K"]

# printing original list
print("The original list is : " + str(test_list))

# initializing values dictionary
val_dict = {"M": 1000000, "B": 1000000000, "Cr": 10000000,
            "L": 100000, "K": 1000, "Tr": 1000000000000}

res = []
for ele in test_list:
    for key in val_dict:
        if key in ele:

            # conversion of dictionary keys to values
            val = float(ele.replace(key, "")) * val_dict[key]
            res.append(val)

# printing result
print("The resolved dictionary values : " + str(res))
```

**输出:**

> 原列表为:['25Cr '，' 7M '，' 24B '，' 9L '，' 2Tr '，' 17K']
> 解析后的字典值:【2500000000.0，7000000.0，2400000000.0，900000.0，20000000000.0，17000.0】