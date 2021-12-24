# Python 中的上下文变量

> 原文:[https://www.geeksforgeeks.org/context-variables-in-python/](https://www.geeksforgeeks.org/context-variables-in-python/)

Python 中的上下文变量对象是一种有趣的变量类型，它根据上下文返回变量值。根据单线程或执行中的上下文，它可能有多个值。ContextVar 类存在于 contextvars 模块中，该模块用于声明和处理 python 中的上下文变量。

**注意:**python 版本> = 3.7 支持。

以下是声明复杂变量的简单语法:

> **语法** contextvars.ContextVar(名称，默认)
> 
> **参数:**
> 
> *   **名称:**可用于引用或调试过程的变量名称。
> *   **默认值:**返回该变量在特定上下文中的值。如果上下文中没有值，那么它将返回默认值。
> 
> **返回:** contextvars 类对象。

**注意:**上下文变量应该总是在程序的顶部创建，永远不要在程序的函数或中间块创建。

以下是在 ContextVar 类中定义的方法:

> 1.  **get ():** Returns the value of a context variable in a specific context. If it does not contain any value, it will return the provided default value (if provided), otherwise it will cause a lookup error.
> 2.  **set (value):** This method is called to set a new value provided as a parameter in the specific context of the calling context variable.
> 3.  **reset (token):** This method refers to the token returned by the set () method, and resets the value of the context variable to the value before calling ContextVar.set ().

**示例:**

## 蟒蛇 3

```
# import module
import contextvars

# declaring the variable 
# to it's default value
cvar = contextvars.ContextVar("cvar",
                              default = "variable")

print("value of context variable cvar: \n",
      cvar.get())

# calling set method
token = cvar.set("changed")

print("\nvalue after calling set method: \n",
      cvar.get())

# checking the type of token instance
print("\nType of object instance returned by set method: \n",
      type(token))

# calling the reset method.
cvar.reset(token)

print("\nvalue after calling reset method: \n",
      cvar.get())
```

**输出:**

```
value of context variable cvar: 
variable

value after calling set method: 
changed

Type of object instance returned by set method: 
<class 'Token'>

value after calling reset method: 
variable

```

### **上下文变量中的令牌类:**

令牌对象由 ContextVar.set()方法返回，并且可以在 ContextVar.reset(令牌)方法中作为参数重用，以将其值重置为上一个令牌上下文变量，如上所述。

以下是可用于令牌对象的属性:

1.  **Token.var:** 它返回用于创建这个由 CotextVar.set()方法返回的令牌的 ContextVar 对象。此具有只读属性，不可调用。
2.  **Token.old_value:** 设置为变量在调用 ContextVar.set()方法之前的值，因为该方法生成了令牌。它是不可调用的，它具有只读属性。它指向令牌。如果在调用之前没有设置变量，则为 MISSING。
3.  **令牌。缺失:**通过 Token.old_value 用作标记。

**示例:**

## 蟒蛇 3

```
import contextvars

# declaring the variable
cvar = contextvars.ContextVar("cvar", default = "variable")

# calling set function to get a token object
token = cvar.set("changed")

# token.var returns the ContextVar
# object through which token is generated.
print("ContextVar object though which token was generated: ")
print(token.var)

# As only one time set is called
# it should return token.MISSING.
print("\nAfter calling token.old_value : ")
print(token.old_value)

# Recalling set method again to
# test other side of token.old_value
token = cvar.set("changed_2")
print("\nPrinting the value set before set method called last : ")
print(token.old_value)

print("\nThe current value of context variable is : ")
print(cvar.get())
```

**输出:**

```
ContextVar object though which token was generated:
<ContextVar name='cvar' default='variable' at 7f82d7c07048>

After calling token.old_value : 
<object object at 0x7f8305801720>

Printing the value set before set method called last : 
changed 

The current value of context variable is : 
changed_2

```

### contextvars 中的上下文类:

contextvars 模块中的这个上下文类是上下文变量到其值的映射。这也可以称为手动上下文管理器。

下面是这个类的一些方法:

> *   **Context ():** Create an empty context with no value.
> *   **get ():** If an assignment is made, the value of the current variable is returned; otherwise, the given default value is returned; otherwise, None is returned.
> *   **keys ():** Returns a list of all variables in the contextvars object.
> *   **Items ():** Returns a list of tuples with two elements in each tuple, first of all, the names of variables, and secondly, the values of all variables in the contextvars object.
> *   **len ():** Returns the number of variables in the contextvars object.
> *   **Values ():** Returns the list of values of all variables in the contextvars object.
> *   **ITER ():** Returns an iterator object, which iterates over all variables existing in the contextvars object.
> *   **copy _ context ():** Returns a light copy of the current contextvars object.
> *   **run (callable, *args, **kwargs):** Execute the function callable(*args, * * kwargs) in the context where the run method is called, which returns the result of the program in the callable function.