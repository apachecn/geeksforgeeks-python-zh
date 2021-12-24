# 使用 Python 删除谷歌浏览器历史记录

> 原文:[https://www . geesforgeks . org/delete-Google-browser-history-using-python/](https://www.geeksforgeeks.org/delete-google-browser-history-using-python/)

在本文中，您将学习编写一个 Python 程序，该程序将把用户的输入作为关键词，如脸书、亚马逊、极客博客、Flipkart、youtube 等。然后在你的谷歌浏览器历史中搜索这个关键词，如果在任何一个网址中找到这个关键词，它就会删除它。比如，假设你输入了关键字‘geeksforgeeks’，那么它会搜索你的谷歌 chrome 历史，比如‘www . geekforgeks . org’，很明显这个 URL 包含了关键字‘geeksforgeeks’，那么它就会删除它，它还会搜索文章(比如“geeksforgeeks 是准备竞争性编程面试的好门户吗？”)标题中包含“geeksforgeeks”并删除它。首先，获取谷歌 chrome 历史文件在你的系统中的位置。

**注意:** Google chrome 历史文件在 windows 中的位置一般为:C:\ Users \ manishkc \ AppData \ Local \ Google \ Chrome \ User Data \ Default \ History。

**实施:**

```py
import sqlite3

# establish the connection with
# history database file which is 
# located at given location
# you can search in your system 
# for that location and provide 
# the path here
conn = sqlite3.connect("/path/to/History")

# point out at the cursor
c = conn.cursor()

# create a variable id 
# and assign 0 initially
id = 0  

# create a variable result 
# initially as True, it will
# be used to run while loop
result = True

# create a while loop and put
# result as our condition
while result:

    result = False

    # a list which is empty at first,
    # this is where all the urls will
    # be stored
    ids = []

    # we will go through our database and 
    # search for the given keyword
    for rows in c.execute("SELECT id,url FROM urls\
    WHERE url LIKE '%geeksforgeeks%'"):

        # this is just to check all
        # the urls that are being deleted
        print(rows)

        # we are first selecting the id
        id = rows[0]

        # append in ids which was initially
        # empty with the id of the selected url
        ids.append((id,))

    # execute many command which is delete
    # from urls (this is the table)
    # where id is ids (list having all the urls)
    c.executemany('DELETE from urls WHERE id = ?',ids)

    # commit the changes
    conn.commit()

# close the connection 
conn.close()
```

**输出:**

```py
(16886, 'https://www.geeksforgeeks.org/')
```