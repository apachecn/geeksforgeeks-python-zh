# Python 中的 EAFP 原理

> 原文:[https://www.geeksforgeeks.org/eafp-principle-in-python/](https://www.geeksforgeeks.org/eafp-principle-in-python/)

EAFP 是 Python 社区中的一条宝贵建议，其他社区的程序员可能不太熟悉。很快， **EAFP** 或 ***【请求原谅比请求允许容易】*** 意味着对你正在处理的代码持有乐观的看法，如果抛出异常，抓住它，稍后处理。

> “永远记住，道歉比获得许可容易得多。在这个计算机的世界里，最好的办法就是去做。”格蕾丝·赫柏

它不同于传统的 **LBYL** 或者**T3【三思而后行】T5【的方法，你检查你的代码是否会成功，并且只有在没有错误的情况下才继续。**

**示例:**假设您想要打开一个文件并读取其内容。

**“许可”代码:**

```py
import os

# Race condition
File_name ="test.txt"

if os.access(File_name, os.R_ok):
    with open(File_name) as f:
        print(f.read())
else:
    print("No such file accessed") 
```

当你请求允许阅读该文件时，答案是“是”，但当你真正去阅读时，答案就变了。这是你向比赛状态敞开自己的地方。

**“原谅”代码:**你应该做的是继续流程并请求原谅，即使用异常处理捕捉错误。

```py
# No Race condition
File_name ="test.txt"

try:
    f = open(File_name)
except IOError:
    print("No such file accessed") 
else:
    with f:
        print(f.read())
```

**EAFP 方法的优势:**

*   显性比隐性好
*   失败，但失败得越快，成功得越快
*   失败，但失败得很便宜
*   不要重复自己