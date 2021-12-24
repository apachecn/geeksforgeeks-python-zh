# 如何用 Python 从网页下载所有图片？

> 原文:[https://www . geesforgeks . org/如何从 python 网页下载所有图像/](https://www.geeksforgeeks.org/how-to-download-all-images-from-a-web-page-in-python/)

**先决条件:**

*   [**请求**](https://www.geeksforgeeks.org/python-requests-tutorial/)
*   [**【美丽的脉冲星】**](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)
*   [**【OS】**](https://www.geeksforgeeks.org/os-module-python-examples/)
*   [**文件处理**](https://www.geeksforgeeks.org/file-handling-python/)

网页抓取是一种从网站获取数据的技术。在网上冲浪时，许多网站不允许用户保存数据供个人使用。一种方法是手动复制粘贴数据，这既繁琐又耗时。网页抓取是从网站提取数据过程的自动化。在本文中，我们将讨论如何使用 python 从网页下载所有图像。

### 需要的模块

*   **bs4:** 美人汤(bs4)是一个从 HTML 和 XML 文件中拉出数据的 Python 库。这个模块没有内置 Python。
*   **请求:** Requests 可以让你极其轻松地发送 HTTP/1.1 请求。该模块也没有内置 Python。
*   **os:**python 中的 OS 模块提供了与操作系统交互的功能。操作系统，属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

### **接近**

*   导入模块
*   获取 HTML 代码
*   在靓汤中使用**查找**方法从 HTML 代码中获取 **img** 标签列表。

```py
images = soup.findAll('img')
```

在操作系统中使用 **mkdir** 方法创建单独的文件夹下载图像。

```py
os.mkdir(folder_name)
```

*   遍历所有图像，获取该图像的源网址。
*   获取源网址后，最后一步是下载图片
*   获取图像内容

```py
r = requests.get(Source URL).content
```

*   使用文件处理下载图像

```py
# Enter File Name with Extension like jpg, png etc..
with open("File Name","wb+") as f:
      f.write(r)
```

**程序:**

## 蟒蛇 3

```py
from bs4 import *
import requests
import os

# CREATE FOLDER
def folder_create(images):
    try:
        folder_name = input("Enter Folder Name:- ")
        # folder creation
        os.mkdir(folder_name)

    # if folder exists with that name, ask another name
    except:
        print("Folder Exist with that name!")
        folder_create()

    # image downloading start
    download_images(images, folder_name)

# DOWNLOAD ALL IMAGES FROM THAT URL
def download_images(images, folder_name):

    # initial count is zero
    count = 0

    # print total images found in URL
    print(f"Total {len(images)} Image Found!")

    # checking if images is not zero
    if len(images) != 0:
        for i, image in enumerate(images):
            # From image tag ,Fetch image Source URL

                        # 1.data-srcset
                        # 2.data-src
                        # 3.data-fallback-src
                        # 4.src

            # Here we will use exception handling

            # first we will search for "data-srcset" in img tag
            try:
                # In image tag ,searching for "data-srcset"
                image_link = image["data-srcset"]

            # then we will search for "data-src" in img
            # tag and so on..
            except:
                try:
                    # In image tag ,searching for "data-src"
                    image_link = image["data-src"]
                except:
                    try:
                        # In image tag ,searching for "data-fallback-src"
                        image_link = image["data-fallback-src"]
                    except:
                        try:
                            # In image tag ,searching for "src"
                            image_link = image["src"]

                        # if no Source URL found
                        except:
                            pass

            # After getting Image Source URL
            # We will try to get the content of image
            try:
                r = requests.get(image_link).content
                try:

                    # possibility of decode
                    r = str(r, 'utf-8')

                except UnicodeDecodeError:

                    # After checking above condition, Image Download start
                    with open(f"{folder_name}/images{i+1}.jpg", "wb+") as f:
                        f.write(r)

                    # counting number of image downloaded
                    count += 1
            except:
                pass

        # There might be possible, that all
        # images not download
        # if all images download
        if count == len(images):
            print("All Images Downloaded!")

        # if all images not download
        else:
            print(f"Total {count} Images Downloaded Out of {len(images)}")

# MAIN FUNCTION START
def main(url):

    # content of URL
    r = requests.get(url)

    # Parse HTML Code
    soup = BeautifulSoup(r.text, 'html.parser')

    # find all images in URL
    images = soup.findAll('img')

    # Call folder create function
    folder_create(images)

# take url
url = input("Enter URL:- ")

# CALL MAIN FUNCTION
main(url)
```

**输出:**

<video class="wp-video-shortcode" id="video-530581-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201211190257/FreeOnlineScreenRecorderProject1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201211190257/FreeOnlineScreenRecorderProject1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201211190257/FreeOnlineScreenRecorderProject1.mp4)</video>