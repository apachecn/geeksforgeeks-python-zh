# 如何比较 python 中的两个文本文件？

> 原文:[https://www . geesforgeks . org/如何比较 python 中的两个文本文件/](https://www.geeksforgeeks.org/how-to-compare-two-text-files-in-python/)

Python 提供了操作文件的方法，这些方法也非常简洁。在本文中，我们将讨论 Python 文件处理特性的一个应用，即文件比较。

**正在使用的文件:**

*   [文本文件 1](https://drive.google.com/file/d/1-7hdNl7nEsSlLnb6FFj26lmU9YlECeG7/view?usp=sharing)
*   [文本文件 2](https://drive.google.com/file/d/1zzVsvKuTVoTFCUDMtsoV32AT4ryRVr5n/view?usp=sharing)

### **方法 1:一次比较完整文件**

Python 支持一个名为 filecmp 的模块，该模块有一个方法 [filecmp.cmp()](https://www.geeksforgeeks.org/python-filecmp-cmp-method/) ，该方法返回三个列表，其中包含匹配的文件、不匹配的文件以及关于那些无法比较的文件的错误。该方法可以在两种模式下运行:

*   **浅模式:**仅比较文件的元数据，如大小、修改日期等。
*   **深度模式:**比较文件内容的地方。

> **语法:**
> 
> 《议定书》/《公约》缔约方会议(a，b)
> 
> **参数:**
> 
> a 和 b 是进行比较的两个数字。
> 
> **返回:**
> 
> *   -1 如果 a
> *   如果 a=b，则为 0
> *   1 如果 a>b

**程序:**

## 蟒蛇 3

```py
import filecmp

f1 = "C:/Users/user/Documents/intro.txt"
f2 = "C:/Users/user/Desktop/intro1.txt"

# shallow comparison
result = filecmp.cmp(f1, f2)
print(result)
# deep comparison
result = filecmp.cmp(f1, f2, shallow=False)
print(result)
```

**输出:**

> 错误的
> 
> 错误的

### **方法二:逐行对比文件**

上述方法的缺点是我们不能检索文件不同的行。虽然这是一个可选的要求，但我们通常希望注意文件中不同的行，然后对其进行操作，使其对我们有利。实现这一点的基本方法是将每个文件的每一行存储在单独的列表中，每个文件一行。这些列表一次与两个文件进行比较。

**进场:**

*   打开要比较的文件
*   循环浏览文件，比较两个文件的每一行。
*   如果行相同，在输出屏幕上输出**相同**。
*   否则，在输出屏幕上输出两个文件的不同行。

**程序:**

## 蟒蛇 3

```py
# reading files
f1 = open("C:/Users/user/Documents/intro.txt", "r")  
f2 = open("C:/Users/user/Desktop/intro1.txt", "r")  

i = 0

for line1 in f1:
    i += 1

    for line2 in f2:

        # matching line1 from both files
        if line1 == line2:  
            # print IDENTICAL if similar
            print("Line ", i, ": IDENTICAL")       
        else:
            print("Line ", i, ":")
            # else print that line from both files
            print("\tFile 1:", line1, end='')
            print("\tFile 2:", line2, end='')
        break

# closing files
f1.close()                                       
f2.close()                                      
```

**输出:**

![](img/4737266fd80b117b4bf1bed6dc06f7ed.png)

### **方法三:比较完整目录**

Python 支持一个名为 filecmp 的模块，该模块使用 filecmp.cmpfiles()方法返回三个列表，其中包含匹配的文件、不匹配的文件以及无法比较的文件的相关错误。它类似于第一种方法，但用于比较两个不同目录中的文件。

**程序:**

## 蟒蛇 3

```py
import filecmp

d1 = "C:/Users/user/Documents/"
d2 = "C:/Users/user/Desktop/"
files = ['intro.txt']

# shallow comparison
match, mismatch, errors = filecmp.cmpfiles(d1, d2, files)
print('Shallow comparison')
print("Match:", match)
print("Mismatch:", mismatch)
print("Errors:", errors)

# deep comparison
match, mismatch, errors = filecmp.cmpfiles(d1, d2, files, shallow=False)
print('Deep comparison')
print("Match:", match)
print("Mismatch:", mismatch)
print("Errors:", errors)
```

**输出:**

> 浅比较
> 
> 匹配:[ ]
> 
> 不匹配:[ ' intro.txt ']
> 
> 错误:[ ]
> 
> 深度比较
> 
> 匹配:[]
> 
> 不匹配:[ ' intro.txt ']
> 
> 错误:[ ]