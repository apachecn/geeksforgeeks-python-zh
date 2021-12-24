# 使用 Python 搜索文件

> 原文:[https://www.geeksforgeeks.org/file-searching-using-python/](https://www.geeksforgeeks.org/file-searching-using-python/)

当您想要搜索系统时，可能会有许多情况。假设在编写 mp3 播放器时，您可能希望所有的. mp3 文件都存在。下面是如何用简单的方法做到这一点。
这段代码搜索正在运行的文件中的所有文件夹。如果你想要一些其他类型的文件，只需更改扩展名。

```py
# Python code to search .mp3 files in current
# folder (We can change file type/name and path
# according to the requirements.
import os

# This is to get the directory that the program 
# is currently running in.
dir_path = os.path.dirname(os.path.realpath(__file__))

for root, dirs, files in os.walk(dir_path):
    for file in files: 

        # change the extension from '.mp3' to 
        # the one of your choice.
        if file.endswith('.mp3'):
            print (root+'/'+str(file))
```

os 不是 python 中的外部库。所以我觉得这是最简单也是最好的方法。

本文由 [**苏史密斯库马尔**](https://auth.geeksforgeeks.org/profile.php?user=soumith kumar) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。