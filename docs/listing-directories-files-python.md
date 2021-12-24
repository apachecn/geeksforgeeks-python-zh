# 用 Python 列出目录和文件

> 原文:[https://www . geesforgeks . org/listing-directory-files-python/](https://www.geeksforgeeks.org/listing-directories-files-python/)

下面是 Python 中一些重要方法/函数的列表，以及理解本文应该知道的描述。

1.  **len()**–用于统计列表、元组、字符串、字典等数据项的元素(项/字符)数量。
2.  **str()**–用于将数据值(整数、浮点数、列表)转换为字符串。
3.  **abspath()**–它返回作为参数传递的文件/目录名的绝对路径。
4.  **enumerate()**–为传递的 iterable 返回一个枚举对象，该对象可用于通过访问 iterable 的索引来迭代 iterable 的项。
5.  **list()**–用于使用现有的 iterable(列表、元组、字典、集合)创建列表。
6.  **listdir()**–用于列出目录内容。目录的路径作为参数传递。
7.  **is file()**–它检查传递的参数是否表示文件的路径。如果是，则返回**真**否则返回**假**
8.  **isdir()**–它检查传递的参数是否表示目录的路径。如果是，则返回**真**否则返回**假**
9.  **追加()**–用于追加列表中的项目。

请查看下面在交互式 Python 终端上执行的代码，快速浏览上述函数/方法的用法。

```py
>>> nums = [1,2,3,4,5]  # list
>>> name = "Alexander"
>>> details = {"name": "Hemkesh", "age": 23, "active": True}
>>> 
>>> # Using len()
... 
>>> len(nums)
5
>>> len(name)
9
>>> len(details)
3
>>> 
>>> # Using str()
... 
>>> str(12)
'12'
>>> str(nums)
'[1, 2, 3, 4, 5]'
>>> str(details)
"{'active': True, 'age': 23, 'name': 'Hemkesh'}"
>>> 
>>> # Using abspath()
... 
>>> import os
>>> os.listdir(".")
['Django', 'Prep', 'python-the-snake']
>>> os.path.abspath("./Django")    # pass ".\Django" on windows
'/Users/admin/projects/Python/Django'
>>> os.path.abspath("Django")
'/Users/admin/projects/Python/Django'
>>> 
>>> # Using enumerate()
...
>>> enumerate(nums)
<enumerate object at 0x100620b90>
>>> 
>>> for index, item in  enumerate(nums):
...     print index, item
... 
0 1
1 2
2 3
3 4
4 5
>>> 
>>> # Using list()
...
>>> list()
[]
>>> list(details )
['active', 'age', 'name']
>>> list(name)
['A', 'l', 'e', 'x', 'a', 'n', 'd', 'e', 'r']
>>> 
>>> # Using isfile() & isdir()
... 
>>> os.path.isdir("Django")
True
>>> os.path.isfile("Django")
False
>>>
>>> os.path.isdir("./python-the-snake/README.md")
False
>>> os.path.isfile("./python-the-snake/README.md")
True
>>> 
>>> # Using append()
...
>>> nums.append(12)
>>> nums
[1, 2, 3, 4, 5, 12]
>>> nums.append(67)
>>> nums
[1, 2, 3, 4, 5, 12, 67]
>>> 
>>> # Don't press "Run on IDE" button available on right. You will get error  
... # as the statements are already executed on interactive terminal.
...
>>>
```

**不同 OS 上的路径结构**
Windows 使用 **\** (反斜杠)作为路径分隔符，例如 **C:\Users\Desktop\**
基于 Linux 的系统像 MAC OS X，Linux 使用 **/** (正斜杠)，例如 **/Users/Desktop/**

让我们快速概述一下上述方法和函数的工作原理，因为我们在最终程序中使用了这些方法和函数。

```py
# Python version : 2.7.12

# len()
# To count number of items in a list
# To count number of characters in a string
evens = [ 2, 34, 6, 8, 10]
print len(evens)

city = "Bangalore"
print len(city), "\n"

# str() : Converting into string representation
odds = [ 1, 3, 67, 45, 83, 59]
year = 2017

print odds
print str(odds) + " A list.\n"  
print year
print str(year) + " A year.\n"

# enumerate() : iterating over index & value of a list
for (index, item) in enumerate(odds):
    print index, item

# abspath() : Getting absolute path of passed argument(path)
import os
absolute_path = os.path.abspath(".")
print "\n", absolute_path, "\n"

# isdir() : To check if passed argument is valid directory path
answer = os.path.isdir("/Users/admin/Desktop/js")
print answer

# isfile() : To check if the passed argument is valid file path
answer = os.path.isfile("/Users/admin/Desktop/js/array.js")
print answer, "\n"

# list() : To create list
details = { "name":"Rojert Rendrick", "age":24, "city":"Bangalore" }
keys = list( details )
print keys, "\n"

# append() : Appending items to list
print evens
evens.append(98)
evens.append(64)
print evens, "\n"

# repetition operator(*) on strings
print "Python"*3
print "#"*20
```

输出:

```py
5
9 

[1, 3, 67, 45, 83, 59]
[1, 3, 67, 45, 83, 59] A list.

2017
2017 A year.

0 1
1 3
2 67
3 45
4 83
5 59

/Users/admin/projects/Python/PythonFiles 

True
True 

['city', 'age', 'name'] 

[2, 34, 6, 8, 10]
[2, 34, 6, 8, 10, 98, 64] 

PythonPythonPython
####################

```

**/用户/管理员/项目/Python/Python 文件**里面有大量的 Python 文件和目录，我们将一一列出。

假设当前工作目录是**/用户/管理员/项目/Python/Django/电商-项目/电商-2/src** ，里面有一些文件和文件夹。

对你来说，情况会不同。您只需要传递您想要列出的目录的确切路径。

下面是根据传递的绝对或相对路径显示所有文件和目录的 python 代码。

如果在调用语句中没有指定路径，那么将显示当前工作目录的内容。

```py
# This Python code is for Python version   : 2.7.12

def show_directories(dir_list, path):
    """ A function that lists the directories """
    import os
    s = "%s%d%s"%("\n", len(dir_list), " directories of " + os.path.abspath(path))
    l = len(s)
    print s
    print "="*l
    for index, dir in enumerate(dir_list):
        print str(index+1) + ") ", dir

def show_files(file_list, path):
    """ A function that lists the files """

    import os
    s = "%s%d%s"%("\n", len(file_list), " files of " + os.path.abspath(path))
    l = len(s)
    print s
    print "="*l
    for index, file in enumerate(file_list):
        print str(index+1) + ") ", file

def show_cwd_contents( path="." ):
    # A function that calls 2 functions to separately 
    # listing out directories and files.
    # It takes a default argument as cwd(.). We can 
    # pass other paths too.
    import os

    f_list = []
    d_list = list()

    try:
        for f in os.listdir(path):
            if os.path.isfile(os.path.join(path, f)):
                f_list.append(f)
            else:
                if os.path.isdir(os.path.join(path, f)):
                    d_list.append(f)
    except:
        print "\nError, once check the path"
        return

    show_files(f_list, path)

    show_directories(d_list, path)

if __name__ == "__main__":

    # If this module is imported in other module then 
    # we need to separately call show_cwd_contents() Or 
    # show_cwd_contents(path).
    show_cwd_contents()
    show_cwd_contents("/Users/admin/projects/Python/PythonFiles")
```

输出:

```py
5 files of /Users/admin/projects/Python/Django/E-Commerce-projects/ecommerce-2/src
===================================================================================
1)  .gitignore
2)  db.sqlite3
3)  manage.py
4)  requirements.txt
5)  todo.txt

5 directories of /Users/admin/projects/Python/Django/E-Commerce-projects/ecommerce-2/src
=========================================================================================
1)  ecommerce2
2)  newsletter
3)  products
4)  static_in_pro
5)  templates

70 files of /Users/admin/projects/Python/PythonFiles
=====================================================
1)  2_list_iterators.py
2)  app.py
3)  class_script_exec.py
4)  class_variables.py
5)  date_and_time.py
6)  datetime.txt
7)  dict.py
8)  dictionary.py
9)  django_home.html
10)  error_handling.py
11)  error_handling_output.py
12)  error_handling_output.txt
13)  execution_pickle.py
14)  fb_task.py
15)  for.py
16)  gfg_sum_of_primes_in_numbers.py
17)  hackerrank_numbers.py
18)  hck_addition_aint_simple.py
19)  hck_biased_chandan.py
20)  hck_c_counts.py
21)  hck_c_counts2.py
22)  hck_c_counts3.py
23)  hck_cool_numbers.py
24)  hck_earth_fans.py
25)  hck_earth_fans_2.py
26)  hck_earth_fans_3.py
27)  hck_earth_fans_final_on_28_dec_2016.py
28)  hck_Little_Jhool_and_psychic_powers.py
29)  hck_lonely_monk.py
30)  hck_lonely_monk_orig.py
31)  hck_maximum_AND.py
32)  hck_min_max_problem.py
33)  hck_monk_and_power_of_time.py
34)  hck_numbers_rotation.py
35)  hck_palindomic_numbers.py
36)  hck_print_hackerearth.py
37)  hck_print_hackerearth_2_way.py
38)  hck_range_query.py
39)  hck_recursive_functions.py
40)  hck_recursive_sums.py
41)  hck_strange_addition.py
42)  hck_sum_of_numbers.py
43)  interactive_img_resolutions.txt
44)  json.py
45)  json.pyc
46)  katyperry.py
47)  lambda_expression.py
48)  linked_list_delete_nodes_at_front.py
49)  linked_list_delete_nodes_at_front_output.txt
50)  linked_list_is_palindrome_gfg.py
51)  linked_list_is_palindrome_gfg_output.text
52)  linked_list_is_palindrome_gfg_testing.py
53)  linked_list_node_deletion_from_any_position.txt
54)  linked_list_node_deletion_from_end.py
55)  linked_list_node_deletion_from_end_output.txt
56)  linked_list_node_deletion_from_middle.py
57)  linked_list_node_insertion_at_beginning.py
58)  linked_list_node_insertion_at_end.py
59)  linked_list_node_insertion_at_middel_output.txt
60)  linked_list_node_insertion_at_middle.py
61)  map.py
62)  merge_lists.py
63)  mufeez_android_interview.py
64)  python_for_loops.py
65)  python_for_loops2.py
66)  remove_dupliates.py
67)  show_dir_and_files.py
68)  show_dir_and_files_test.py
69)  smarika_urllib_python2.7.10.py
70)  while.py

2 directories of /Users/admin/projects/Python/PythonFiles
==========================================================
1)  socket_programming
2)  wx

```

本文由 **Rishikesh Agrawani** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。