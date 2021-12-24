# python–etrtools . cycle()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-etrtools-cycle/

迭代器被定义为对象类型，它包含可以使用循环访问或迭代的值。Python 内置了不同的迭代器，如列表、集合等。Itertools 是 Python 模块，包含一些使用迭代器生成序列的内置函数。这个模块提供了各种处理迭代器的函数来产生复杂的迭代器。这个模块作为一个快速、内存高效的工具，可以单独使用，也可以组合使用，形成迭代器代数。

迭代器有不同的类型

*   **Infinite Iterators: These type of iterators produce infinite sequences.** *   ****短序列迭代器:******These iterators produces the sequences which terminate after certain iterations.
***   组合学生成器函数:**These generators produce the sequences in combinations related to the input arguments.

## itertools . cycle()

*   该函数只接受一个参数作为输入，它可以像列表、字符串、元组等
*   函数返回迭代器对象类型
*   在函数的实现中，返回类型是 yield，它在不破坏局部变量的情况下暂停函数的执行。它由产生中间结果的生成器使用
*   它遍历输入参数中的每个元素并产生它，重复循环并产生一个无穷序列的参数

下面提到的 Python 程序说明了循环函数的功能。它以字符串类型作为参数，并产生无限序列。

```
import itertools

# String for sequence generation
Inputstring ="Geeks"

# Calling the function Cycle from
# itertools and passing string as 
#an argument and the function returns
# the iterator object
StringBuffer = itertools.cycle(Inputstring)
SequenceRepeation = 0
SequenceStart = 0
SequenceEnd = len(Inputstring)

for output in StringBuffer:
    if(SequenceStart == 0):
        print("Sequence % d"%(SequenceRepeation + 1))

    # Cycle function iterates through each
    # element and produces the sequence 
    # and repeats it the sequence
    print(output, end =" ")

    # Checks the End of the Sequence according 
    # to the give input argument
    if(SequenceStart == SequenceEnd-1):

        if(SequenceRepeation>= 2):
            break
        else:
            SequenceRepeation+= 1
            SequenceStart = 0
            print("\n")
    else:
        SequenceStart+= 1
```

**输出:**

```
Sequence  1
G e e k s 

Sequence  2
G e e k s 

Sequence  3
G e e k s

```

itertools.cycle 函数也适用于 Python 列表。下面提到的 Python 程序说明了它的功能。它以 Python 列表为参数，生成无限序列。

```
import itertools

# List for sequence generation
Inputlist = [1, 2, 3]

# Calling the function Cycle from
# itertools and passing list as 
# an argument and the function 
# returns the iterator object
ListBuffer = itertools.cycle(Inputlist)
SequenceRepeation = 0
SequenceStart = 0
SequenceEnd = len(Inputlist)

for output in ListBuffer:
    if(SequenceStart == 0):
        print("Sequence % d"%(SequenceRepeation + 1))

    # Cycle function iterates through 
    # each element and produces the 
    # sequence and repeats it the sequence
    print(output, end =" ")

    # Checks the End of the Sequence according
    # to the give input argument
    if(SequenceStart == SequenceEnd-1):

        if(SequenceRepeation>= 2):
            break
        else:
            SequenceRepeation+= 1
            SequenceStart = 0
            print("\n")
    else:
        SequenceStart+= 1
```

**输出:**

```
Sequence  1
1 2 3 

Sequence  2
1 2 3 

Sequence  3
1 2 3 

```**