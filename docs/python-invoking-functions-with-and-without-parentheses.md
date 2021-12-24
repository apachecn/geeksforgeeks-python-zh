# Python–调用带括号和不带括号的函数

> 原文:[https://www . geesforgeks . org/python-调用带括号和不带括号的函数/](https://www.geeksforgeeks.org/python-invoking-functions-with-and-without-parentheses/)

Python 中的函数是执行特定任务的已定义代码块。在本节中，我们将讨论使用和不使用括号调用函数的区别。

*   当我们调用带有括号的**函数时，*函数得到执行*并将结果返回给可调用的。**
*   在另一种情况下，当我们调用不带括号的**函数时，*函数引用被发送到可调用的*而不是执行函数本身。**

让我们讨论 3 个重要概念:

*   调用函数
*   返回函数
*   传递函数

## 调用函数–

下面的函数执行一个简单的任务，字符串连接。在这里，我们将调用带括号和不带括号的函数“concatenate_string ”,看看它们的区别。

```
def concatenate_string(*args):
    string1 = args[0]
    string2 = args[1]

    return string1 + string2

obj = concatenate_string('Hello, ', 'George')
print('Function call with Parentheses: ')
print(obj)

obj = concatenate_string
print('Function call without Parentheses: ')
print(obj)
```

**输出**

```
Function call with Parentheses: 
Hello, George
Function call without Parentheses:
<function concatenate_string at 0x7f0bb991df28>

```

对于第一种情况，当我们调用`concatenate_string('Hello, ', 'George')`时，函数执行并返回连接的字符串。
对于第二种情况，当我们调用`concatenate_string`时，即不带括号，引用被传递给可调用的，而不是执行函数本身。在这里，可调用函数可以决定如何处理引用。

## 返回功能–

从上面的讨论中，您可以理解，当用括号调用函数时，代码被执行并返回结果。并且，当它在没有括号的情况下被调用时，函数引用被返回给可调用的。
那么，当一个函数和一个带括号和不带括号的返回语句一起编码时会发生什么。让我们来看一个例子。

**带括号**

```
def concatenate_string(*args):

    string1 = args[0]
    string2 = args[1]

    def merge_string(string1, string2):
        return string1 + string2

    return merge_string(string1, string2)

def func():
    conc_obj = concatenate_string('Hello, ', 'George')
    print(conc_obj)

func()
```

**输出**

```
Hello, George
```

从上面的例子中，很明显`merge_string`是函数`concatenate_string`中的一个函数，主函数(`concatenate_string`)将子函数(`merge_string`)返回给调用者。

```
 return merge_string(string1, string2) 
```

这里`merge_string`用括号调用，因此它执行并将结果提供给`concatenate_string`，从这里将结果传递给`func`。

**不带括号**

```
def concatenate_string():

    def merge_string(string1, string2):
        return string1 + string2

    return merge_string

def func():

    # return the reference of merge_string func
    conc_obj = concatenate_string()
    print(conc_obj)  # prints the reference 

    # executes the reference 
    print(conc_obj('Hello, ', 'George'))  

func()
```

**输出:**

```
<function concatenate_string..merge_string at 0x7f1e54ebc158>
Hello, George

```

由于使用的`merge_string`没有括号，`concatenate_string`将函数引用传递给可调用的`func`，而不是执行`merge_string`。

```
return merge_string
```

因此，我们可以得出这样的结论:当我们在返回语句中用括号编码子函数时，主函数执行子函数，并将结果传递给可调用函数。
而且，当我们在 return 语句中编写不带括号的子函数时，主函数会将子函数引用传递给可调用的，而不是执行它。在这里，可调用函数决定如何处理引用。

## 传递函数–

您可以通过创建引用、调用不带括号的函数并将其作为参数来传递函数作为参数。让我们看看代码。

```
def concatenate_string(*args):
    string1 = args[0]
    string2 = args[1]

    def merge_string(string1, string2):
        return string1 + string2  # string merge

    # executes merge_string and return the result
    return merge_string(string1, string2)

def function_call(function):
    string1 = 'Hello, '
    string2 = 'George'
    return function(string1, string2)

# passing function as argument
print(function_call(concatenate_string))  
```

**输出:**

```
Hello, George
```

在这种情况下，`concatenate_string`的引用作为参数传递给`function_call`。

```
function_call(concatenate_string)
```

在 function_call 内部，它使用引用执行`concatenate_string`，并将结果返回给可调用的。