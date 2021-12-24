# 程序打印自己的名字作为输出

> 原文:[https://www . geesforgeks . org/program-to-print-自有名称作为输出/](https://www.geeksforgeeks.org/program-to-print-its-own-name-as-output/)

有没有想过写一个脚本，当你执行它时，它会打印出自己的名字。很简单。你一定注意到了主功能是这样写的程序

```
int main(int argc, char** argv)
```

你一定想知道这两个论点是什么意思。

*   The first *argc* is the number of parameters passed to your program.
*   The second *argv* is an array that holds all the parameter names passed into the program.
*   In addition to these parameters, there is an extra piece of information stored in the first cell of the array, namely argv[0], which is the full path of the file containing the code.

要打印程序的名称，我们需要做的就是把文件名从路径中切掉。

**实施**

下面是上面讨论的想法的 python 实现。让我们假设脚本的名称是 print_my_name。

```
# Python program to prints it own name upon execution
import sys

def main():
    program = sys.argv[0] # argv[0] contains the full path of the file

    # rfind() finds the last index of backslash
    # since in a file path the filename comes after the last '\'
    index = program.rfind("\\") + 1

    # slicing the filename out of the file path
    program = program[index:]
    print("Program Name: % s" % program)

# executes main
if __name__ == "__main__":
    main()
```

```
Output: print_my_name.py
```

**注意:**在 GeeksforGeeks 在线编译器上运行时，输出会有所不同。

本文由 [Palash Nigam](https://www.linkedin.com/in/palash25) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。