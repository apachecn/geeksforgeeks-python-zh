# Python 中的内置异常

> 原文:[https://www.geeksforgeeks.org/built-exceptions-python/](https://www.geeksforgeeks.org/built-exceptions-python/)

Python 中的所有实例都必须是从 **BaseException** 派生的类的实例。通过子类化不相关的两个异常类从来都不是等价的，即使它们有相同的名字。内置异常可以由解释器或内置函数生成。

Python 中有几个内置的异常，在出现错误时会引发。这些内置异常可以使用 **local()** 内置函数查看，如下所示:

```py
>>> locals()['__builtins__']

```

这将返回内置异常、函数和属性的字典。

**基类**

以下异常主要用作其他异常的基类。

1.  **异常 BaseException**
    这是所有内置异常的基类。它并不意味着由用户定义的类直接继承。对于用户定义的类，使用异常。此类负责使用 str()和传递的参数创建异常的字符串表示形式。如果没有参数，则返回空字符串。
    *   **参数:**参数是给异常构造函数的参数元组。
    *   **with_traceback(tb) :** This method is usually used in exception handling. This method sets tb as the new traceback for the exception and returns the exception object.

        **代码:**

        ```py
        try:
            ...
        except SomeException:
            tb = sys.exc_info()[2]
            raise OtherException(...).with_traceback(tb)

        ```

2.  **异常**
    这是所有内置非系统退出异常的基类。所有用户定义的异常也应该从此类派生。
3.  **exception ArithmeticError**
    This class is the base class for those built-in exceptions that are raised for various arithmetic errors such as :
    *   OverflowError
    *   零分割错误
    *   浮动指针错误

    **示例:**

    ```py
    try:  
        a = 10/0  
        print (a)
    except ArithmeticError:  
            print ("This statement is raising an arithmetic exception.")
    else:  
        print ("Success.")
    ```

    **输出:**

    ```py
    This statement is raising an arithmetic exception.

    ```

4.  **异常缓冲错误**
    当无法执行缓冲相关操作时，会引发此异常。
5.  **异常 LookupError**
    这是当映射或序列上使用的键或索引无效或找不到时引发的异常的基类。提出的例外是:

*   键错误
*   索引错误

**示例:**

```py
try: 
    a = [1, 2, 3] 
    print (a[3]) 
except LookupError: 
    print ("Index out of bound error.")
else: 
    print ("Success")

```

**输出:**

```py
Index out of bound error.

```

**具体例外情况**

以下异常是通常引发的异常。

1.  **exception AssertionError**
    An AssertionError is raised when an assert statement fails.

    **示例:**

    ```py
    assert False, 'The assertion failed'

    ```

    **输出:**

    ```py
    Traceback (most recent call last):
      File "exceptions_AssertionError.py", line 12, in 
        assert False, 'The assertion failed'
    AssertionError: The assertion failed

    ```

2.  **exception AttributeError**
    An AttributeError is raised when an attribute reference or assignment fails such as when a non-existent attribute is referenced.

    **示例:**

    ```py
    class Attributes(object):
        pass

    object = Attributes()
    print (object.attribute)
    ```

    **输出:**

    ```py
    Traceback (most recent call last):
      File "d912bae549a2b42953bc62da114ae7a7.py", line 5, in 
        print object.attribute
    AttributeError: 'Attributes' object has no attribute 'attribute'

    ```

3.  **exception EOFError**
    An EOFError is raised when built-in functions like input() hits an end-of-file condition (EOF) without reading any data. The file methods like readline() return an empty string when they hit EOF.

    **示例:**

    ```py
    while True:
        data = input('Enter name : ')
        print ('Hello  ', data)
    ```

    **输出:**

    ```py
    Enter Name :Hello Aditi
    Enter Name :Traceback (most recent call last):
      File "exceptions_EOFError.py", line 13, in 
        data = raw_input('Enter name :')
    EOFError: EOF when reading a line

    ```

4.  **exception FloatingPointError**
    A FloatingPointError is raised when a floating point operation fails. This exception is always defined, but can only be raised when Python is configured with the–with-fpectl option, or the WANT_SIGFPE_HANDLER symbol is defined in the pyconfig.h file.

    **示例:**

    ```py
    import math

    print (math.exp(1000))
    ```

    **输出:**

    ```py
    Traceback (most recent call last):
      File "", line 1, in 
    FloatingPointError: in math_1

    ```

5.  **exception GeneratorExit**
    This exception directly inherits from BaseException instead of Exception since it is technically not an error. A GeneratorExit exception is raised when a generator or coroutine is closed.

    **示例:**

    ```py
    def my_generator():
        try:
            for i in range(5):
                print ('Yielding', i)
                yield i
        except GeneratorExit:
            print ('Exiting early')

    g = my_generator()
    print (g.next())
    g.close()

    ```

    **输出:**

    ```py
    Yielding 0
    0
    Exiting early

    ```

6.  **异常导入错误**
    当导入语句无法加载模块时，或者当来自…导入中的“来自列表”的名称找不到时，会引发导入错误。

**示例:**

```py
import module_does_not_exist
```

**输出:**

```py
Traceback (most recent call last):
  File "exceptions_ImportError_nomodule.py", line 12, in 
    import module_does_not_exist
ImportError: No module named module_does_not_exist

```

**示例:**

```py
from exceptions import Userexception
```

**输出:**

```py
Traceback (most recent call last):
  File "exceptions_ImportError_missingname.py", line 12, in 
    from exceptions import Userexception
ImportError: cannot import name Userexception

```

*   **异常 modulentfounderror**
    这是 ImportError 的子类，当找不到模块时，导入会引发该子类。当在系统模块中找不到时，也会引发此问题*   **exception IndexError**
    An IndexError is raised when a sequence is referenced which is out of range.

    **示例:**

    ```py
    array = [ 0, 1, 2 ]
    print (array[3])
    ```

    **输出:**

    ```py
    Traceback (most recent call last):
      File "exceptions_IndexError.py", line 13, in 
        print array[3]
    IndexError: list index out of range

    ```

    *   **exception KeyError**
    A KeyError is raised when a mapping key is not found in the set of existing keys.

    **示例:**

    ```py
    array = { 'a':1, 'b':2 }
    print (array['c'])
    ```

    **输出:**

    ```py
    Traceback (most recent call last):
      File "exceptions_KeyError.py", line 13, in 
        print array['c']
    KeyError: 'c'

    ```

    *   **exception KeyboardInterrupt**
    This error is raised when the user hits the interrupt key such as Control-C or Delete.

    **示例:**

    ```py
    try:
        print ('Press Return or Ctrl-C:',)
        ignored = input()
    except Exception, err:
        print ('Caught exception:', err)
    except KeyboardInterrupt, err:
        print ('Caught KeyboardInterrupt')
    else:
        print ('No exception')
    ```

    **输出:**

    ```py
    Press Return or Ctrl-C: ^CCaught KeyboardInterrupt

    ```

    *   **exception MemoryError**
    This error is raised when an operation runs out of memory.

    **示例:**

    ```py
    def fact(a):
        factors = []
        for i in range(1, a+1):
            if a%i == 0:
                factors.append(i)
        return factors 

    num = 600851475143
    print (fact(num))
    ```

    **输出:**

    ```py
    Traceback (most recent call last):
      File "4af5c316c749aff128df20714536b8f3.py", line 9, in 
        print fact(num)
      File "4af5c316c749aff128df20714536b8f3.py", line 3, in fact
        for i in range(1, a+1):
    MemoryError

    ```

    *   **exception NameError**
    This error is raised when a local or global name is not found. For example, an unqualified variable name.

    **示例:**

    ```py
    def func():
        print ans

    func()
    ```

    **输出:**

    ```py
    Traceback (most recent call last):
      File "cfba0a5196b05397e0a23b1b5b8c7e19.py", line 4, in 
        func()
      File "cfba0a5196b05397e0a23b1b5b8c7e19.py", line 2, in func
        print ans
    NameError: global name 'ans' is not defined

    ```

    *   **exception NotImplementedError**
    This exception is derived from RuntimeError. Abstract methods in user defined classed should raise this exception when the derived classes override the method.

    **示例:**

    ```py
    class BaseClass(object):
        """Defines the interface"""
        def __init__(self):
            super(BaseClass, self).__init__()
        def do_something(self):
            """The interface, not implemented"""
            raise NotImplementedError(self.__class__.__name__ + '.do_something')

    class SubClass(BaseClass):
        """Implementes the interface"""
        def do_something(self):
            """really does something"""
            print (self.__class__.__name__ + ' doing something!')

    SubClass().do_something()
    BaseClass().do_something()
    ```

    **输出:**

    ```py
    Traceback (most recent call last):
      File "b32fc445850cbc23cd2f081ba1c1d60b.py", line 16, in 
        BaseClass().do_something()
      File "b32fc445850cbc23cd2f081ba1c1d60b.py", line 7, in do_something
        raise NotImplementedError(self.__class__.__name__ + '.do_something')
    NotImplementedError: BaseClass.do_something

    ```

    *   **exception OSError([arg])**
    The OSError exception is raised when a system function returns a system-related error, including I/O failures such as “file not found” or “disk full” errors.

    **示例:**

    ```py
    def func():
        print (ans)

    func()
    ```

    **输出:**

    ```py
    Traceback (most recent call last):
      File "442eccd7535a2704adbe372cb731fc0f.py", line 4, in 
        print i, os.ttyname(i)
    OSError: [Errno 25] Inappropriate ioctl for device

    ```

    *   **exception OverflowError**
    The OverflowError is raised when the result of an arithmetic operation is out of range. Integers raise MemoryError instead of OverflowError. OverflowError is sometimes raised for integers that are outside a required range. Floating point operations are not checked because of the lack of standardization of floating point exception handling in C.

    **示例:**

    ```py
    import sys

    print ('Regular integer: (maxint=%s)' % sys.maxint)
    try:
        i = sys.maxint * 3
        print ('No overflow for ', type(i), 'i =', i)
    except OverflowError, err:
        print ('Overflowed at ', i, err)

    print()
    print ('Long integer:')
    for i in range(0, 100, 10):
        print ('%2d' % i, 2L ** i)

    print()
    print ('Floating point values:')
    try:
        f = 2.0**i
        for i in range(100):
            print (i, f)
            f = f ** 2
    except OverflowError, err:
        print ('Overflowed after ', f, err)
    ```

    **输出:**

    ```py
    Regular integer: (maxint=9223372036854775807)
    No overflow for   i = 27670116110564327421

    Long integer:
     0 1
    10 1024
    20 1048576
    30 1073741824
    40 1099511627776
    50 1125899906842624
    60 1152921504606846976
    70 1180591620717411303424
    80 1208925819614629174706176
    90 1237940039285380274899124224

    Floating point values:
    0 1.23794003929e+27
    1 1.53249554087e+54
    2 2.34854258277e+108
    3 5.5156522631e+216
    Overflowed after  5.5156522631e+216 (34, 'Numerical result out of range')

    ```

    *   **异常递归错误**
    递归错误源于运行时错误。当解释器检测到超过最大递归深度时，会引发此异常。*   **异常引用错误**
    当垃圾收集后使用弱引用代理访问引用对象的属性时，会引发引用错误。

**示例:**

```py
import gc
import weakref

class Foo(object):

    def __init__(self, name):
        self.name = name

    def __del__(self):
        print ('(Deleting %s)' % self)

obj = Foo('obj')
p = weakref.proxy(obj)

print ('BEFORE:', p.name)
obj = None
print ('AFTER:', p.name)
```

**输出:**

```py
BEFORE: obj
(Deleting )
AFTER:

Traceback (most recent call last):
  File "49d0c29d8fe607b862c02f4e1cb6c756.py", line 17, in 
    print 'AFTER:', p.name
ReferenceError: weakly-referenced object no longer exists

```

*   **异常运行时间错误**
    当没有其他异常适用时，会引发运行时间错误。它返回一个字符串，精确地指示出了什么问题。*   **exception StopIteration**
    The StopIteration error is raised by built-in function next() and an iterator‘s __next__() method to signal that all items are produced by the iterator.

    **示例:**

    ```py
    Arr = [3, 1, 2]
    i=iter(Arr)

    print (i)
    print (i.next())
    print (i.next())
    print (i.next())
    print (i.next())
    ```

    **输出:**

    ```py

    3
    1
    2

    Traceback (most recent call last):
      File "2136fa9a620e14f8436bb60d5395cc5b.py", line 8, in 
        print i.next()
    StopIteration

    ```

    *   **exception SyntaxError**
    The SyntaxError is raised when the parser encounters a syntax error. A syntax error may occur in an import statement or while calling the built-in functions exec() or eval(), or when reading the initial script or standard input.

    **示例:**

    ```py
    try:
        print (eval('geeks for geeks'))
    except SyntaxError, err:
        print ('Syntax error %s (%s-%s): %s' % \
            (err.filename, err.lineno, err.offset, err.text))
        print (err)
    ```

    **输出:**

    ```py
    Syntax error  (1-9): geeks for geeks
    invalid syntax (, line 1)

    ```

    *   **异常系统错误**
    当解释器发现内部错误时，会引发系统错误。相关联的值是一个字符串，指示出了什么问题。*   **异常系统退出**
    调用 sys.exit()函数时，系统退出被引发。对 sys.exit()的调用被转换为异常，以执行清理处理程序(try 语句的 finally 子句)和调试脚本，而不会冒失去控制的风险。*   **异常类型错误**
    当对不适当类型的对象应用操作或函数时，会引发类型错误。此异常返回一个字符串，给出类型不匹配的详细信息。

**示例:**

```py
arr = ('tuple', ) + 'string'
print (arr)
```

**输出:**

```py
Traceback (most recent call last):
  File "30238c120c0868eba7e13a06c0b1b1e4.py", line 1, in 
    arr = ('tuple', ) + 'string'
TypeError: can only concatenate tuple (not "str") to tuple

```

*   **exception UnboundLocalError**
    UnboundLocalError is a subclass of NameError which is raised when a reference is made to a local variable in a function or method, but no value has been assigned to that variable.

    **示例:**

    ```py
    def global_name_error():
        print (unknown_global_name)

    def unbound_local():
        local_val = local_val + 1
        print (local_val)

    try:
        global_name_error()
    except NameError, err:
        print ('Global name error:', err)

    try:
        unbound_local()
    except UnboundLocalError, err:
        print ('Local name error:', err)
    ```

    **输出:**

    ```py
    Global name error: global name 'unknown_global_name' is not defined
    Local name error: local variable 'local_val' referenced before assignment

    ```

    *   **异常 UnicodeError**
    这个异常是 ValueError 的一个子类。发生与 Unicode 相关的编码或解码错误时，会引发 UnicodeError。*   **exception ValueError**
    A ValueError is raised when a built-in operation or function receives an argument that has the right type but an invalid value.

    **示例:**

    ```py
    print (int('a'))
    ```

    **输出:**

    ```py
    Traceback (most recent call last):
      File "44f00efda935715a3c5468d899080381.py", line 1, in 
        print int('a')
    ValueError: invalid literal for int() with base 10: 'a'

    ```

    *   **exception ZeroDivisionError**
    A ZeroDivisionError is raised when the second argument of a division or modulo operation is zero. This exception returns a string indicating the type of the operands and the operation.

    **示例:**

    ```py
    print (1/0)
    ```

    **输出:**

    ```py
    Traceback (most recent call last):
      File "c31d9626b41e53d170a78eac7d98cb85.py", line 1, in 
        print 1/0
    ZeroDivisionError: integer division or modulo by zero

    ```

本文由**阿迪提·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。