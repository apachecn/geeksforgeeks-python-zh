# 使用 Python 中的 Regex 将 10 位电话号码转换为美国格式

> 原文:[https://www . geeksforgeeks . org/converting-a-10 位数电话号码-us-format-use-regex-in-python/](https://www.geeksforgeeks.org/converting-a-10-digit-phone-number-to-us-format-using-regex-in-python/)

[文本预处理](https://www.geeksforgeeks.org/text-preprocessing-in-python-set-1/)是自然语言处理中最重要的任务之一。您可能想从字符串中提取数字。为这样的处理任务编写一个手动脚本需要大量的努力，而且在大多数时候它很容易出错。考虑到这些预处理任务的重要性，正则表达式的概念已经在不同的编程语言中被开发出来，以便于这些文本处理任务。

为了实现[正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)，可以使用 python **re** 包，要使用它，可以像任何其他内置 python 模块一样轻松导入。

**将 10 位电话号码转换为相应美国号码格式的步骤:**

*   导入 python re 包。
*   编写一个函数，将要格式化的电话号码作为参数并对其进行处理。
*   现在只需调用函数并传递值。

**示例:**

## 蟒蛇 3

```
import re 

def convert_phone_number(phone):

  # actual pattern which only change this line
  num = re.sub(r'(?<!\S)(\d{3})-', r'(\1) ', phone) 
  return num

# Driver code 
print(convert_phone_number("Call geek 321-963-0612"))
```

**输出:**

```
Call geek (321) 963-0612
```