# 如何退出 Python 脚本？

> 原文:[https://www.geeksforgeeks.org/how-to-exit-a-python-script/](https://www.geeksforgeeks.org/how-to-exit-a-python-script/)

退出 python 脚本是指终止活动 Python 进程的过程。更实际地说，它通常是对程序的函数(或析构函数)退出例程的调用。每当 python 脚本完成执行(或可执行代码用完)时，这个过程都会隐式完成，但也可以通过使用某些函数来调用。在本文中，我们将了解退出 python 程序，在退出程序之前执行任务，以及在显示自定义(错误)消息时退出程序。

## **退出 Python 应用程序**

存在几种退出 python 应用程序的方式。以下[篇](https://www.geeksforgeeks.org/python-exit-commands-quit-exit-sys-exit-and-os-_exit/)对其中一些进行了非常详细的解释。彻底阅读它将教育用户何时使用哪种方法，以及哪种方法最适合他们的特定用例。一般来说，它们的功能或多或少是相同的，即退出 python 程序。有些函数可以正常工作(调用清理例程、刷新缓冲区、关闭文件对象等)。)和其他人残忍地这样做(没有前面提到的步骤)。使用内置方法通常更好，因为只需要在需要的地方调用它们。

**示例:**

## 蟒蛇 3

```py
print("this is the first statement")

exit()

print("this is the second statement")
```

**输出:**

```py
this is the first statement
```

## 检测脚本退出

有时需要在 python 脚本终止之前执行某些任务。为此，需要检测脚本何时要退出。 *atexit* 是一个用于执行该任务的模块。该模块用于定义注册和取消注册清理功能的函数。代码执行后会调用清理函数。默认的清理函数用于清理代码执行所产生的残余，但是我们将使用它来执行我们的定制代码。

在下面的代码中，我们将定义(并注册)一个在程序终止时调用的函数。首先，导入 atexit 模块。然后定义 exit_handler()函数。该函数包含一个打印语句。稍后，通过将函数对象传递给 *atexit.register()* 函数来注册该函数。最后还有一个调用打印功能显示 *GFG！*在输出。在输出中，第一行是代码中最后一个 print 语句的输出。第二行包含在代码执行时调用的 *exit_handler* 函数的输出(作为一个清理函数)。

并非所有类型的退出都由 atexit 模块处理。

**示例:**

## 蟒蛇 3

```py
import atexit

def exit_handler():
    print('My application is ending!')

atexit.register(exit_handler)

print('GFG!')
```

**输出:**

```py
GFG
My application is ending!
```

## **无错误退出**

有时我们只对程序的执行或终止感兴趣，而不是其中遇到的任何错误。如果我们能够捕捉到执行过程中遇到的任何异常或错误，这是可能的。这可以通过在一般的 try-except 块中使用 except:子句来实现。我们将利用这样一个事实，即一个裸异常不仅可以捕获异常，甚至可以捕获在 try 块执行期间遇到的某些中断和错误。

在实际代码中，裸机除外条款通常是不可取的。原因是它也隐藏了代码中产生的几种类型的错误。这种行为可能会让调试代码变得有些忙乱。因此，应该谨慎使用它，并且只有当 try 子句中的代码不容易出错时(这在大多数情况下不是一个合理的假设)。

**示例:**

## 蟒蛇 3

```py
def main():
    asdfgh
    print("HELLO WORLD!")

if __name__ == "__main__":
    try:
        main()

    except:
        print("Gotcha!")
```

**输出:**

```py
Gotcha!
```

## **错误退出**

通常，当 python 程序遇到错误时，它会在控制台屏幕上显示错误。但是有时我们对在显示一些表示可能发生的错误的文本时退出应用程序感兴趣。这个过程也可以用来退出程序并在最后显示一些文本。在下面的代码中，我们将在显示一些文本后退出 python 程序。

这里可以提供一个字符串或整数作为 exit()函数的参数。如果参数是字符串(表示错误消息等)，那么它将在程序执行后输出。如果它是一个整数，那么它应该是一个 POSIX 退出代码。

**示例:**

## 蟒蛇 3

```py
print("Hello world!")

exit("__PUT_ERROR_MSG_HERE__")
```

**输出:**

```py
Hello world!
__PUT_ERROR_MSG_HERE__
```