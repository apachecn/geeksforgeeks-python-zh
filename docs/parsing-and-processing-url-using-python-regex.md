# 使用 Python-Regex 解析和处理网址

> 原文:[https://www . geeksforgeeks . org/解析和处理-URL-使用-python-regex/](https://www.geeksforgeeks.org/parsing-and-processing-url-using-python-regex/)

**先决条件:**[**Python 中的正则表达式**](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

****网址**或**统一资源定位器**由许多信息部分组成，如域名、路径、端口号等。任何网址都可以使用正则表达式进行处理和解析。所以为了使用正则表达式，我们必须使用 Python 中的 **re** 库。**

****示例:****

```
**URL:** https://www.geeksforgeeks.org/courses
When we parse the above URL then we can find

**Hostname**: geeksforgeeks.com
**Protocol:** https 
```

**我们正在使用 re 库的 **re.findall( )** 函数在 URL 中搜索需要的模式。**

> ****语法:** re.findall(正则表达式，字符串)**
> 
> ****返回:**字符串中模式的所有非重叠匹配，作为字符串列表。**

**现在，让我们看看例子:**

****示例 1:** 在本例中，我们将从给定的 URL 中提取协议和主机名。**

*   **提取协议组的正则表达式:“**(\ w+)://**”**。****
*   **提取主机名组的正则表达式:' **://www。([\w\-\。]+)** ' **。****

****使用的元字符:****

*   ****\w:** 匹配任意字母数字字符，这相当于类[a-zA-Z0-9_]。**
*   ****+:** 一次或多次出现以前的字符。**

****代码:****

## **蟒蛇 3**

```
# import library
import re  

# url link
s = 'https://www.geeksforgeeks.org/'

# finding the protocol 
obj1 = re.findall('(\w+)://',
                  s)
print(obj1)

# finding the hostname which may
# contain dash or dots
obj2 = re.findall('://www.([\w\-\.]+)', 
                  s)
print(obj2)
```

****输出:****

```
['https']
['geeksforgeeks.org'] 
```

****示例 2:** 如果 URL 是不同的类型，如“**文件://localhost:4040/zip_file** ”，并带有端口号，那么为了提取端口号，由于它是可选的，我们将使用**“？”**符号。这里，端口号'**4040′**出现在 **':'** 符号之后。因此，由于是数字 **(:(\d+))** 被使用。由于并非所有 URL 都以主机号结尾，因此要将其设为可选，请使用以下语法 **'(:(\d+)？。****

****使用的元字符:****

*   ****\d:** 匹配任意十进制数字，这相当于集合类[0-9]。**
*   ****+:** 一次或多次出现以前的字符。**
*   ****？:**匹配零个或一个事件。**

****代码:****

## **蟒蛇 3**

```
# import library
import re  

# url link
s = 'file://localhost:4040/abc_file'

# finding the file capture group
obj1 = re.findall('(\w+)://', s)  
print(obj1)

# finding the hostname which may 
# contain dash or dots
obj2 = re.findall('://([\w\-\.]+)', s)
print(obj2)

# finding the hostname which may 
# contain dash or dots or port
# number
obj3 = re.findall('://([\w\-\.]+)(:(\d+))?', s)
print(obj3)
```

****输出:****

```
['file']
['localhost']
[('localhost', ':4040', '4040')] 
```

****示例 3:** 对于一般的 URL，可以使用这个，其中也可以构造路径元素。**

## **蟒蛇 3**

```
# import library
import re

# url
s = 'http://www.example.com/index.html' 

# searching for all capture groups
obj = re.findall('(\w+)://([\w\-\.]+)/(\w+).(\w+)',
                 s)

print(obj)
```

****输出:****

```
[('http', 'www.example.com', 'index', 'html')]
```