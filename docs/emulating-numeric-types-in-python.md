# 在 Python 中模拟数字类型

> 原文:[https://www . geesforgeks . org/仿真-python 中的数字类型/](https://www.geeksforgeeks.org/emulating-numeric-types-in-python/)

以下是可以定义来模拟数字类型对象的函数。

### 在相同类型的对象上实现二进制操作的方法:

这些函数不会改变调用对象，而是在对调用对象执行某些操作后返回一个相同类型的新数值对象。以下是实现[算术二进制运算的方法。](https://www.geeksforgeeks.org/python-operators/)

<figure class="table">

| **方法** | **操作** |
| *对象。__ 添加 _ _(自我，其他)* | **+** (加法) |
| *对象。__sub__(自身，其他)* | **–**(减法) |
| *对象。__mul__(自身，其他)* | ***** (乘法) |
| *对象。__matmul__(自我，其他)* | **@** (矩阵乘法) |
| *对象。__truediv__(自我，其他)* | **/** (真除法) |
| *对象。__floordiv__(自身，其他)* | **/**(楼层划分) |
| *对象。__mod__(自身，其他)* | **%** (模数或余数) |
| *对象。__divmod__(自身，其他)* | [时尚()](https://www.geeksforgeeks.org/divmod-python-application/) |
| *对象。__ 幂 _ _(自身，其他[，模])* | ****** (电源) |
| *对象。_ _ lshift _ _(自我，其他)* | **< <** (逐位左移) |
| *对象。__rshift__(自身，其他)* | **> >** (按位右移) |
| *对象。__ 和 _ _(自我，其他)* | **&** (位智与运算) |
| *对象。__xor__(自身，其他)* | **^** (异或运算) |
| *对象。__ 或 _ _(自我，其他)* | **&#124;** (位相或运算) |

</figure>

__pow__()被定义为接受第三个可选参数，以便支持 pow()函数的三进制版本。此外，如果上述任何方法不支持该操作，则应返回 ***未执行的*** 。

### 在不同类型的对象上实现二进制操作的方法:

如果左侧对象(可折叠对象)的类型不同，则可以使用以下方法执行[算术二进制运算](https://www.geeksforgeeks.org/python-operators/):

<figure class="table">

| **方法** | **操作** |
| *对象。__radd__(自身，其他)* | **+** (加法) |
| *对象。__rsub__(自我，其他)* | **–**(减法) |
| *对象。__rmul__(自身，其他)* | ***** (乘法) |
| *对象。__rmatmul__(自身，其他)* | **@** (矩阵乘法) |
| *对象。__rtruediv__(自身，其他)* | **/** (真除法) |
| *对象。__rfloordiv__(自身，其他)* | **/**(楼层划分) |
| *对象。__rmod__(自身，其他)* | **%** (模数或余数) |
| *对象。__rdivmod__(自身，其他)* | [时尚()](https://www.geeksforgeeks.org/divmod-python-application/) |
| *对象。__rpow__(自身，其他[，模])* | ****** ( [幂(](https://www.geeksforgeeks.org/pow-in-python/))或数的幂) |
| *对象。__rlshift__(自身，其他)* | **< <** (逐位左移) |
| *对象。__rrshift__(自身，其他)* | **> >** (按位右移) |
| *对象。__ 兰德 _ _(自我，其他)* | **&** (位智与运算) |
| *对象。__rxor__(自身，其他)* | **^** (异或运算) |
| *对象。__ror__(自身，其他)* | **&#124;** (位相或运算) |

</figure>

例如，如果在 a _ sub _ _(b)中，从 b 开始，a 不是数字类型，那么这个方法将返回 *NotImplemented，*然后为了执行 a–b，我们将调用 a _ rsub _ _(b)。

### 实现算术赋值运算的方法:

这些方法用于实现[算术赋值运算](https://www.geeksforgeeks.org/python-operators/)。它们不会返回新的对象，而是在调用对象本身时分配新的值。像 ***x.__imul__(y)*** 将作为 ***x = x * y*** 执行。以下是每种方法的相应操作。

<figure class="table">

| **方法** | **操作** |
| *对象。__iadd__(自身，其他)* | **+=** (加法赋值) |
| *对象。__isub__(自身，其他)* | **-=** (减法赋值) |
| *对象。__imul__(自身，其他)* | ***=** (乘法赋值) |
| *对象。__imatmul__(自我，其他)* | **@=** (矩阵乘法赋值) |
| *对象。__itruediv__(自身，其他)* | **/=** (真除法赋值) |
| *对象。__ifloordiv__(自身，其他)* | **//=** (楼层划分分配) |
| *对象。__imod__(自我，其他)* | **%=** (模数或余数赋值) |
| *对象。__ipow__(自身，其他[，模])* | ****=** ( [数字的力量](https://www.geeksforgeeks.org/pow-in-python/) r 分配) |
| *对象。__ilshift__(自身，其他)* | **< < =** (逐位左移分配) |
| *对象。__irshift__(自身，其他)* | **> > =** (逐位右移赋值) |
| *对象。__ 和 _ _(自身，其他)* | **& =** (逐位与运算赋值) |
| *对象。__ixor__(自身，其他)* | **^=** (操作分配的专用) |
| *对象。__ior__(自我，其他)* | **&#124;=** (位相或运算分配) |

</figure>

### 实现一元算术运算的方法:

以下是实现一元算术运算的方法，如，一个数的负数，一个数的倒数等。

<figure class="table">

| **方法** | **操作** |
| *对象。__neg__(自我)* | **–**(一元减) |
| *对象。__pos__(自我)* | **+** (一元加号) |
| *对象。__abs__(自我)* | [**【ABS()**](https://www.geeksforgeeks.org/abs-in-python/#:~:text=Itertools.Permutations()-, abs()%20in%20Python, absolute%20value%20of%20a%20number.&text=If%20the%20argument%20is%20an, be%20a%20floating%20point%20number.)内置功能 |
| *对象。__ 反转 _ _(自)* | **~** (一个数的补码) |

</figure>

### 其他一些重要的方法:

<figure class="table">

| **方法** | **描述** |
| *对象。__ 指数 _ _(自我)* | 调用以实现*运算符. index()* 函数，也用于将数值类型对象转换为整数类型，或者我们可以说，如果 __int__()，__float__()或 __complex__()没有定义，那么 int()，float()和 complex()就会下降在 __index__()下。 |
| *对象。__round__(self，ndigits)* | 要实现 [**round()函数**](https://www.geeksforgeeks.org/round-function-python/#:~:text=Python%20in%202020%3F-, round()%20function%20in%20Python, number%20to%20the%20nearest%20integer.) ，第二个可选参数告诉最多多少个小数位我们想要取整数值。 |
| *对象。__trunc__(自我)* | 要实现 [**trunc()功能。**T3】](https://www.geeksforgeeks.org/g-fact-35-truncate-in-python/) |
| *对象。__ 楼层 _ _(自)* | 要实现 [**楼层()功能。**T3】](https://www.geeksforgeeks.org/floor-ceil-function-python/#:~:text=The%20method%20ceil()%20in, integer%20not%20less%20than%20x.) |
| *对象。__ceil__(自我)* | 要实现 [**ceil()功能。**T3】](https://www.geeksforgeeks.org/floor-ceil-function-python/#:~:text=The%20method%20ceil()%20in, integer%20not%20less%20than%20x.) |

</figure>