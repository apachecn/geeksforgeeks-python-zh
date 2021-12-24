# 获取 GitHub | Python

上的前 10 大明星用户存储库

> 原文:[https://www . geesforgeks . org/fetch-top-10-starred-repositories-user-github-python/](https://www.geeksforgeeks.org/fetch-top-10-starred-repositories-user-github-python/)

**先决条件:**对[巨蟒](https://www.geeksforgeeks.org/python-language-introduction/)、urllib2、[的基本了解](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)

我们经常编写 python 脚本来简化我们的任务，所以这里有一个脚本可以帮助你获取 GitHub 上任何用户的前 10 个星级存储库。
运行脚本只需要 Github 用户名(例如: [msdeep14](https://github.com/msdeep14) )即可。
**剧本说明:**

1.  首先访问用户的存储库 url，例如:username =“msdeep 14”，然后 URL = "https://github.com/msdeep14？tab =存储库”
2.  现在刮取 url 页面，并使用美化组获取星星、存储库名称和存储库 url。
3.  在一个页面上有 30 个存储库，所以如果用户有超过 30 个存储库，你需要一个循环来访问所有的页面。
4.  使用 urllib2 或 BeautifulSoup 来刮页面，代码两者都使用，请参见下面的代码。

## 大蟒

```
# Python3 script to fetch top 10 starred
# repositories of a user on github
import urllib.request, urllib.parse, urllib.error
import urllib.request, urllib.error, urllib.parse
import http.cookiejar
import requests
from lxml import html
from lxml import etree
from bs4 import BeautifulSoup
import re
import operator

top_limit = 9

def openWebsite():

    # enter Github username
    # of user
    username = str(input("enter GitHub username: "))

    # Dictionary to store key as repository
    # name and value as no. of stars
    repo_dict = {}

    # This is first page url where user
    # repositories are located
    url = "https://github.com/"+username+"?tab=repositories"

    # loop for all the pages
    while True:

        '''
            You can read the docs of urllib2 and
            BeautifulSoup to see how html page
            can be scraped to extract data

            urllib2  : https://docs.python.org/2/library/urllib2.html
            BeautifulSoup : https://www.crummy.com/software/BeautifulSoup/bs4/doc/
        '''

        # open the website and get
        # the html of webpage into doc
        cj = http.cookiejar.CookieJar()
        opener = urllib.request.build_opener(urllib.request.HTTPCookieProcessor(cj))
        resp = opener.open(url)
        doc = html.fromstring(resp.read())

        # extract all the repository names
        repo_name = doc.xpath('//li[@class="col-12 d-block width-full py-4 border-bottom public source"]/div[@class="d-inline-block mb-1"]/h3/a/text()')

        # list to store repository names
        repo_list = []

        # get the repository name
        for name in repo_name:
            name = ' '.join(''.join(name).split())
            repo_list.append(name)
            repo_dict[name] = 0

        # print repo_list
        response = requests.get(url)
        soup = BeautifulSoup(response.text, 'html.parser')

        '''
            The path mentioned to get the no. of
            stargazers, you can get it by right
            click on star symbol on Github page,
            and then select inspect element
        '''
        soup = BeautifulSoup(response.text, 'html.parser')
        div = soup.find_all('li', {'class': 'col-12 d-block width-full py-4 border-bottom public source'})

        for d in div:
            temp = d.find_all('div',{'class':'f6 text-gray mt-2'})
            for t in temp:

                # Get the no. of stars of
                # particular repository
                x = t.find_all('a', attrs={'href': re.compile("^\/[a-zA-Z0-9\-\_\.]+\/[a-zA-Z0-9\.\-\_]+\/stargazers")})

                # Get the url of the repository
                # and populate the values of dictionary
                # with no. of stars
                if len(x) is not 0:
                    name = x[0].get('href')
                    name = name[len(username)+2:-11]
                    repo_dict[name] = int(x[0].text)

        # Check if next page exists
        # for more repositories
        div = soup.find('a',{'class':'next_page'})

        # print div
        if div is not None:
            url = div.get('href')
            url = "https://github.com/"+url
        else:
            # if there is no next repository
            # page, then exit loop
            break

    # Get the sorted list of all
    # repos and print top 10
    i = 0
    sorted_repo = sorted(iter(repo_dict.items()), key = operator.itemgetter(1))

    # Print the sorted repos in
    # reverse order
    for val in reversed(sorted_repo):
        repo_url = "https://github.com/" + username + "/" + val[0]
        print("\nrepo name : ",val[0], "\nrepo url  : ",repo_url, "\nstars     : ",val[1])
        i = i + 1
        if i > top_limit:
            break

# Driver program
if __name__ == "__main__":
    openWebsite()
```

输出:

```
enter GitHub username: msdeep14

repo name :  DeepDataBase 
repo url  :  https://github.com/msdeep14/DeepDataBase 
stars     :  13

repo name :  MiniDataBase 
repo url  :  https://github.com/msdeep14/MiniDataBase 
stars     :  8

repo name :  hackerranksolutions 
repo url  :  https://github.com/msdeep14/hackerranksolutions 
stars     :  6

repo name :  stayUpdated 
repo url  :  https://github.com/msdeep14/stayUpdated 
stars     :  6

repo name :  IRCTC 
repo url  :  https://github.com/msdeep14/IRCTC 
stars     :  4

repo name :  play_2048 
repo url  :  https://github.com/msdeep14/play_2048 
stars     :  3

repo name :  Tripcount 
repo url  :  https://github.com/msdeep14/Tripcount 
stars     :  3

repo name :  SnapLook 
repo url  :  https://github.com/msdeep14/SnapLook 
stars     :  2

repo name :  fbFun 
repo url  :  https://github.com/msdeep14/fbFun 
stars     :  2

repo name :  ByteCode 
repo url  :  https://github.com/msdeep14/ByteCode 
stars     :  2
```

**视频教程**

<video class="wp-video-shortcode" id="video-176612-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/out.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/out.mp4](https://media.geeksforgeeks.org/wp-content/uploads/out.mp4)</video>

**完整的存储库链接:** [trackGitHubStars](https://github.com/msdeep14/trackGitHubStars)