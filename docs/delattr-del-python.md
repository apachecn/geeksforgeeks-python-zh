# Python 中的 delattr()和 del()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/delaattr-del-python/

delaattr

**delattr()** 方法用于在对象事先许可的情况下，从对象中删除命名属性。
**语法:**

```py
delattr(object, name)

The function takes only two parameter:

object :  from which 
the name attribute is to be removed.
name :  of the attribute 
which is to be removed.

The function doesn't returns any value, 
it just removes the attribute, 
only if the object allows it.
```

**工作类:**假设我们有一个名为 Geek 的类，它有五个学生作为属性。因此，使用 delattr()方法，我们可以移除任何一个属性。

## 蟒蛇 3

```py
# Python code to illustrate delattr()
class Geek:
  stu1 = "Henry"
  stu2 = "Zack"
  stu3 = "Stephen"
  stu4 = "Amy"
  stu5 = "Shawn"

names = Geek()

print('Students before delattr()--')
print('First = ',names.stu1)
print('Second = ',names.stu2)
print('Third = ',names.stu3)
print('Fourth = ',names.stu4)
print('Fifth = ',names.stu5)

# implementing the method
delattr(Geek, 'stu5')

print('After deleting fifth student--')
print('First = ',names.stu1)
print('Second = ',names.stu2)
print('Third = ',names.stu3)
print('Fourth = ',names.stu4)
# this statement raises an error
print('Fifth = ',names.stu5)
```

输出:

```py
Students before delattr()--
First =  Henry
Second =  Zack
Third =  Stephen
Fourth =  Amy
Fifth =  Shawn
After deleting fifth student--
First =  Henry
Second =  Zack
Third =  Stephen
Fourth =  Amy
```

当执行移动到程序的最后一行时，即调用第五个属性时，编译器会引发错误:

```py
Traceback (most recent call last):
  File "/home/028e8526d603bccb30e9aeb7ece9e1eb.py", line 25, in 
    print('Fifth = ',names.stu5)
AttributeError: 'Geek' object has no attribute 'stu5'
```

**del 运算符**

Python 中还有另一个运算符，它的工作类似于 delattr()方法。是 **del** 运算符。让我们看看它是如何工作的。

## 蟒蛇 3

```py
# Python code to illustrate del()
class Geek:
  stu1 = "Henry"
  stu2 = "Zack"
  stu3 = "Stephen"
  stu4 = "Amy"
  stu5 = "Shawn"

names = Geek()

print('Students before del--')
print('First = ',names.stu1)
print('Second = ',names.stu2)
print('Third = ',names.stu3)
print('Fourth = ',names.stu4)
print('Fifth = ',names.stu5)

# implementing the operator
del Geek.stu5

print('After deleting fifth student--')
print('First = ',names.stu1)
print('Second = ',names.stu2)
print('Third = ',names.stu3)
print('Fourth = ',names.stu4)
# this statement raises an error
print('Fifth = ',names.stu5)
```

输出:

```py
Students before del--
First =  Henry
Second =  Zack
Third =  Stephen
Fourth =  Amy
Fifth =  Shawn
After deleting fifth student--
First =  Henry
Second =  Zack
Third =  Stephen
Fourth =  Amy
```

结果相同，但有一个错误:

```py
Traceback (most recent call last):
  File "/home/7c239eef9b897e964108c701f1f94c8a.py", line 26, in 
    print('Fifth = ',names.stu5)
AttributeError: 'Geek' object has no attribute 'stu5'
```

**del vs****【delaattr()**

1.  **动态删除:** del 更加明确高效，delattr()允许动态删除属性。
2.  **速度:**如果考虑以上程序并运行，则执行速度略有差异。根据机器的不同，与 delattr()相比，del 稍快一些**。**
3.  ****字节码指令:** del 与 delattr()相比，也占用更少的字节码指令。**

**因此，我们通过说 del 比 delattr 稍快来结束比较，但是当涉及到属性的动态删除时，delattr()具有优势，因为 del 运算符不可能做到这一点。**