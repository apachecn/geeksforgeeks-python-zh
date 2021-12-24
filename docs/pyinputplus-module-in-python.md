# Python 中的 PyInputPlus 模块

> 原文:[https://www.geeksforgeeks.org/pyinputplus-module-in-python/](https://www.geeksforgeeks.org/pyinputplus-module-in-python/)

**PyInputPlus** 是一个 Python 模块，用于获取具有附加验证功能的输入。 *PyInputPlus* 将继续向用户询问文本，直到他们输入有效的输入。

**安装:**

通过 *pip* 命令安装模块:

```
pip install PyInputPlus

```

以下是用于进行各种类型输入的函数:

*   **T0】 【input num() 【T1]: accept the numerical value. It needs additional parameters "minimum", "maximum", "greater than" and "less than" as boundaries. Returns an int or float.**
*   **inputstr ()** : accept the string value. It provides functions such as "blockRegexes", "Timeout" and "Limit".
*   **Input tint ()** : accept integer values. This also requires additional parameters "minimum", "maximum", "greater than" and "less than" as boundaries. Returns an integer.
*   **Input float ()** : accept floating-point values. Additional Minimum, Maximum, Greater than and Less than parameters are also required. Returns a floating-point number.
*   **Inputbool ()** : accept boolean values. The input can be in any case-insensitive form of "true"/"false" and "t"/"f". Returns a Boolean value.
*   **Input Choice ()** : Get a list of strings and accept one of them as input.
*   **Input menu ()** : Similar to inputChoice (), but the options are displayed as items in the menu. Menu items can be marked with letters or numbers, using "letters" and "numbers" parameters.
*   **Input date ()** : the date when the strftime format is accepted. We need to pass this format to the "formats" parameter. Returns a datetime.date object.
*   **Input time ()** : Time to accept strftime format. Returns a datetime.time object.
*   **inputdatetime ()** : the date and time when strftime format was accepted. Returns a datetime.datetime object.
*   **Enter no ()** : accept case-insensitive Yes/No or Y/N. Return Yes orNo..

#### **一些示例用法:**

**1。字符串输入:**

**inputStr()** 功能用于获取字符串输入。我们可以设置**提示**参数，在输入前定义一个提示。类似于内置功能*输入()*的*提示*参数。通过将**空白**参数设置为*真*，我们可以允许空白值作为有效输入。通过将 **blockRegexes** 参数的值设置为我们想要使其无效的 regex 模式，可以阻止某些输入(即这些值无效)。

## 蟒 3

```
import pyinputplus as pyip

# string input with
# additional parameters
inp = pyip.inputStr(prompt="Enter a string... ", 
                    blank=True, blockRegexes = 'aeiou')

print(inp)
```

**输出:**

```
Enter a string... Hello
This response is invalid.
Enter a string... GFG
GFG

```

**2。整数输入:**

**InputTint()**功能用于进行整数输入。如果传递了任何非整数输入，函数将重试，直到给出有效输入、时间耗尽或超过最大尝试次数。**默认**参数用于在时间耗尽或尝试次数超过时设置默认值。**限制**参数用于指定用户输入有效输入的最大尝试次数，之后返回*默认*值(如果指定的话)，否则将引发 **RetryLimitException** 。

## 蟒 3

```
import pyinputplus as pyip

# integer input with
# limited number of tries
inp = pyip.inputInt(prompt = "Enter an Integer... ", 
                    default = 0, limit = 3)

print(inp)
```