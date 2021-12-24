# 使用 Python 从网络下载文件

> 原文:[https://www . geesforgeks . org/下载-文件-web-使用-python/](https://www.geeksforgeeks.org/downloading-files-web-using-python/)

[Requests](http://docs.python-requests.org/en/master/) 是 python 中的一个多功能 HTTP 库，有多种应用。它的一个应用是使用文件网址从网上下载一个文件。
**安装:**首先，你需要下载请求库。通过键入以下命令，您可以使用 pip 直接安装它:

```py
pip install requests
```

或者直接从[这里](https://pypi.python.org/pypi/requests/2.11.1)下载，手动安装。

**下载文件**

```py
# imported the requests library
import requests
image_url = "https://www.python.org/static/community_logos/python-logo-master-v3-TM.png"

# URL of the image to be downloaded is defined as image_url
r = requests.get(image_url) # create HTTP response object

# send a HTTP request to the server and save
# the HTTP response in a response object called r
with open("python_logo.png",'wb') as f:

    # Saving received content as a png file in
    # binary format

    # write the contents of the response (r.content)
    # to a new file in binary mode.
    f.write(r.content)
```

上面写的这段小代码将从网上下载下面的图片。现在，检查您的本地目录(此脚本所在的文件夹)，您会发现此图像:

我们需要的只是图片来源的网址。(您可以通过右键单击图像并选择查看图像选项来获取图像源的网址。)

**下载大文件**

HTTP 响应内容( **r.content** )只不过是一个存储文件数据的字符串。因此，在大文件的情况下，不可能将所有数据保存在一个字符串中。为了克服这个问题，我们对程序做了一些更改:

*   Since all file data can’t be stored by a single string, we use **r.iter_content** method to load data in chunks, specifying the chunk size.

    ```py
     r = requests.get(URL, stream = True)
    ```

    将**流**参数设置为**真**将只下载响应头，连接保持打开。这避免了将内容一次性读入内存以获得大响应。每次迭代 **r.iter_content** 时都会加载一个固定的块。

    这里有一个例子:

    ```py
    import requests
    file_url = "http://codex.cs.yale.edu/avi/db-book/db4/slide-dir/ch1-2.pdf"

    r = requests.get(file_url, stream = True)

    with open("python.pdf","wb") as pdf:
        for chunk in r.iter_content(chunk_size=1024):

             # writing one chunk at a time to pdf file
             if chunk:
                 pdf.write(chunk)
    ```

    **下载视频**

    在这个例子中，我们有兴趣下载这个[网页](http://www.py4inf.com/)上的所有视频讲座。本次讲座的所有档案都可以在[这里](http://www-personal.umich.edu/~csev/books/py4inf/media/)获得。所以，我们先刮网页提取所有的视频链接，然后逐一下载视频。

    ```py
    import requests 
    from bs4 import BeautifulSoup 

    ''' 
    URL of the archive web-page which provides link to 
    all video lectures. It would have been tiring to 
    download each video manually. 
    In this example, we first crawl the webpage to extract 
    all the links and then download videos. 
    '''

    # specify the URL of the archive here 
    archive_url = "http://www-personal.umich.edu/~csev/books/py4inf/media/"

    def get_video_links(): 

        # create response object 
        r = requests.get(archive_url) 

        # create beautiful-soup object 
        soup = BeautifulSoup(r.content,'html5lib') 

        # find all links on web-page 
        links = soup.findAll('a') 

        # filter the link sending with .mp4 
        video_links = [archive_url + link['href'] for link in links if link['href'].endswith('mp4')] 

        return video_links 

    def download_video_series(video_links): 

        for link in video_links: 

            '''iterate through all links in video_links 
            and download them one by one'''

            # obtain filename by splitting url and getting 
            # last string 
            file_name = link.split('/')[-1] 

            print( "Downloading file:%s"%file_name) 

            # create response object 
            r = requests.get(link, stream = True) 

            # download started 
            with open(file_name, 'wb') as f: 
                for chunk in r.iter_content(chunk_size = 1024*1024): 
                    if chunk: 
                        f.write(chunk) 

            print( "%s downloaded!\n"%file_name )

        print ("All videos downloaded!")
        return

    if __name__ == "__main__": 

        # getting all video links 
        video_links = get_video_links() 

        # download all videos 
        download_video_series(video_links) 

    ```

    使用请求库下载网络文件的优点是:

    *   人们可以通过递归迭代网站来轻松下载网络目录！
    *   这是一个独立于浏览器的方法，而且速度更快！
    *   One can simply scrape a web page to get all the file URLs on a webpage and hence, download all files in a single command-

        [用美图实现 Python 网页抓取
        T2】](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)

    本博客由 Nikhil Kumar 投稿。如果你喜欢极客博客并想投稿，你也可以用 contribute.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。