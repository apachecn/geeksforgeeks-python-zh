# 如何用 Python 从吉拉获取数据？

> 原文:[https://www . geesforgeks . org/如何从 python 中的 jira 获取数据/](https://www.geeksforgeeks.org/how-to-fetch-data-from-jira-in-python/)

吉拉是一个敏捷的项目管理工具，由 Atlassian 开发，主要用于跟踪项目错误和问题。它已经逐渐发展成为一个强大的工作管理工具，可以处理敏捷方法的所有阶段。在本文中，我们将学习如何使用 Python 从吉拉获取数据。

**获取数据有两种方式:**

1.  使用 Python 的 JIRA 库。
2.  使用 JIRA 休息应用编程接口。

**吉拉软件工具中所需的配置如下:**

1.  创建一个[吉拉用户账户](https://id.atlassian.com/login/authorize?token=eyJraWQiOiJtaWNyb3NcL2FpZC1zaWdudXBcL29zaGlrcDM4ZjNxMDJwc2ciLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiJsaW5rLXNpZ25hdHVyZS12YWxpZGF0b3IiLCJtYXJrZWRWZXJpZmllZCI6ImZhbHNlIiwiY3NyZlRva2VuIjoiMDVhZmRlZWM0YjI4YWUzM2JkZWFlN2JjNWUxMzYyOWZkMWQ5ZGE3NSIsIm5iZiI6MTYyMTY3MTY0MCwibG9naW5UeXBlIjoic2Vzc2lvblJlZnJlc2giLCJzY29wZSI6IkxvZ2luIiwiaXNzIjoibWljcm9zXC9haWQtc2lnbnVwIiwiZXhwIjoxNjIxNjcxNzYwLCJ1c2VySWQiOiI2MGE1ZDlkMjliMzYyZjAwNjkxNjRmMzMiLCJpYXQiOjE2MjE2NzE2NDAsImp0aSI6ImU0MWQ0NWQ1LTM4M2QtNGVmYS1iZWJmLWM2Zjc1YzkzNzk1ZSJ9.iBKybIHmEfsSqN9o5likCULZJq6F8hMNDPw7YDSvnBa5ChBCf8WXqVo64bVqIyrnV8miH-jo2JqdDLYaOzIdu2fe0MLt7P8MnaCI41_YvNJWeCSziAmDOCZgcAh8dDstAnLiaJo-kL9i9-Lsq8GLGKcOPWOet4FBqT_XdpoiAHfkqOvuz_khoFy74O6zfu-CgFa3VuCef1iAj0W-7uiI_iexBj7rTGJPN0UeKmsnBZGhqUPF7pgnKKlKTIioYrDrRJJvO_KTOQtfh1D2lA07-HPsfKOkWFV5LVEHgLaM3CtzSKwTm4YplaZJLPi7Kd79dzDKajezp6ADkySvBJCY1g)。
2.  创建一个域名，添加一个项目，并记录一些问题或 bug。我们的任务是使用 Python 代码获取、发布数据。
3.  我们需要从链接[https://id.atlassian.com/manage/api-tokens](https://id.atlassian.com/manage/api-tokens)获得用于认证的有效令牌。

![](img/7d4f086d347156716a8c9e159c1254c8.png)

JIRA 工具中记录的项目“MedicineAppBugs”的问题

**JQL:** JQL 代表吉拉查询语言。这是一种获取 JIRA 相关数据的有效方式。它可以在 JIRA 图书馆和应用编程接口方法中用于获取数据。这包括形成查询，以过滤关于相关 bug、项目、问题等的信息。可以在查询中使用不同运算符和关键字的组合。

## **使用 Python 的吉拉库获取数据**

JIRA 是一个 Python 库，用于连接 JIRA 工具。与应用编程接口方法相比，该库易于使用，用于获取与问题、项目、工作日志等相关的数据。该库需要大于 3.5 的 Python 版本。

**使用命令**安装 jira

```
pip install jira
```

**进场:**

*   导入 jira 模块。
*   使用以下内容构建吉拉客户端实例–
    *   服务器密钥，即您的域名，是在 Atlassian 帐户上创建的。
    *   基本身份验证参数、您注册的电子邮件 ID 和收到的唯一令牌。
*   绕过身份验证参数，获取 JIRA 客户端实例。
*   根据项目名称搜索所有提及的问题(使用打印语句显示详细信息，如问题关键字、摘要、报告者姓名。).

**下面是实现:**

## 计算机编程语言

```
# import the installed Jira library
from jira import JIRA

# Specify a server key. It should be your
# domain name link. yourdomainname.atlassian.net
jiraOptions = {'server': "https://txxxxxxpython.atlassian.net"}

# Get a JIRA client instance, pass,
# Authentication parameters
# and the Server name.
# emailID = your emailID
# token = token you receive after registration
jira = JIRA(options=jiraOptions, basic_auth=(
    "prxxxxxxh@gmail.com", "bj9xxxxxxxxxxxxxxxxxxx5A"))

# Search all issues mentioned against a project name.
for singleIssue in jira.search_issues(jql_str='project = MedicineAppBugs'):
    print('{}: {}:{}'.format(singleIssue.key, singleIssue.fields.summary,
                             singleIssue.fields.reporter.displayName))
```

**输出:**

![](img/35ea0b04d4db5a5607ec9e269fa13543.png)

使用 JIRA 库发布数据输出。

**使用吉拉图书馆，我们还可以获取单个问题的细节。**

密钥是问题的唯一标识，我们需要它的详细信息。在平台上为一个项目添加一个问题后，获取该问题，同时获取单个问题的详细信息，传递其唯一标识或密钥。

## 计算机编程语言

```
# import the installed Jira library
from jira import JIRA

# Specify a server key. It is your  domain 
# name link.
jiraOptions = {'server': "https://txxxxxxpython.atlassian.net"}

# Get a JIRA client instance, Pass 
# Authentication parameters
# and  Server name.
# emailID = your emailID
# token = token you receive after registration
jira = JIRA(options = jiraOptions, 
            basic_auth = ("prxxxxxxh@gmail.com",
                          "bj9xxxxxxxxxxxxxxxxxxx5A"))

# While fetching details of a single issue,
# pass its UniqueID or Key.
singleIssue = jira.issue('MED-1')
print('{}: {}:{}'.format(singleIssue.key,
                         singleIssue.fields.summary,
                         singleIssue.fields.reporter.displayName))
```

**输出:**

![](img/95144849388e3a89eeacf1b393afffcf.png)

使用 JIRA 图书馆的一个问题的细节

## **使用吉拉休息应用编程接口**获取数据

JIRA 服务器平台为问题和工作流提供了 REST 应用编程接口。它允许我们在问题、组、仪表板等上执行 CRUD 操作。针对吉拉 Rest API 的开发者平台是有据可查的，可以参考[https://developer . atlassian . com/cloud/jira/platform/Rest/v2/intro/](https://developer.atlassian.com/cloud/jira/platform/rest/v2/intro/)。基于我们的需求，我们需要在平台上寻找特定的 URI。在下面的代码片段中，我们正在获取我们提到的项目“医疗应用程序错误”的所有问题。

需要 Python 库:

1.  python 发行包中提供了库 JSON。
2.  使用命令–**pip 安装请求安装请求。**
3.  使用命令–**pip 安装熊猫。**

### 获取应用编程接口链接

*   访问[开发者 API。](https://developer.atlassian.com/cloud/jira/platform/rest/v2/intro/)
*   人们可以在左侧面板上找到可供开发人员使用的各种应用编程接口选项。例如，除了问题之外，在“用户”、“项目”上还有用于执行 CRUD 操作的 API。
*   在本文中，我们正在获取所有问题，因此，我们将选择选项“问题搜索”。我们将选择子选项“使用 JQL(GET)方法搜索问题”。
*   选择此选项时，将显示 URI“GET/rest/API/2/search”，以及允许的请求参数格式。
*   附上上述链接，您的域名为–“https://your-domain . atlassian . net/rest/API/2/search”。这个最终的网址，将有助于，获取，所有问题，对我们的项目。

**进场:**

*   导入所需的模块。
*   准备网址，搜索所有问题。
*   使用注册的电子邮件 ID 和收到的令牌创建一个身份验证对象。
*   传递项目名称，在，JQL 查询。如果您省略了 JQL 查询，那么您的域中所有项目的问题将被获取。
*   使用身份验证、头对象和 JQL 查询创建并发送请求对象。
*   使用 JSON loads 方法将 JSON 响应转换为 Python 字典对象。
*   所有问题都作为列表元素出现在主应用编程接口输出的关键“问题”中。因此，循环遍历每个元素。
*   因为，单个问题，单独地，是另一个嵌套的字典对象，使用“迭代字典”函数来获得所需的键。
*   最后，将输出列表附加到 Pandas 的数据框中，并显示它。

注意:请仔细研究应用编程接口输出，检查您需要的字段的位置和类型。它们可以是嵌套字典或列表对象，并且需要相应地决定函数逻辑。

**下面是实现:**

## 计算机编程语言

```
# Import the required libraries
import requests
from requests.auth import HTTPBasicAuth
import json
import pandas as pd

# URL to Search all issues.
url = "https://txxxxxxpython.atlassian.net/rest/api/2/search"

# Create an authentication object,using
# registered emailID, and, token received.
auth = HTTPBasicAuth("prxxxxxxh@gmail.com",
                     "bj9xxxxxxxxxxxxxxxxxxx5A")

# The Header parameter, should mention, the
# desired format of data.
headers = {
    "Accept": "application/json"
}
# Mention the JQL query.
# Here, all issues, of a project, are
# fetched,as,no criteria is mentioned.
query = {
    'jql': 'project =MedicineAppBugs '
}

# Create a request object with above parameters.
response = requests.request(
    "GET",
    url,
    headers=headers,
    auth=auth,
    params=query
)

# Get all project issues,by using the
# json loads method.
projectIssues = json.dumps(json.loads(response.text),
                           sort_keys=True,
                           indent=4,
                           separators=(",", ": "))

# The JSON response received, using
# the requests object,
# is an intricate nested object.
# Convert the output to a dictionary object.
dictProjectIssues = json.loads(projectIssues)

# We will append,all issues,in a list object.
listAllIssues = []

# The Issue details, we are interested in,
# are "Key" , "Summary" and "Reporter Name"
keyIssue, keySummary, keyReporter = "", "", ""

def iterateDictIssues(oIssues, listInner):

    # Now,the details for each Issue, maybe
    # directly accessible, or present further,
    # in nested dictionary objects.
    for key, values in oIssues.items():

        # If key is 'fields', get its value,
        # to fetch the 'summary' of issue.
        if(key == "fields"):

            # Since type of object is Json str,
            # convert to dictionary object.
            fieldsDict = dict(values)

            # The 'summary' field, we want, is 
            # present in, further,nested dictionary
            # object. Hence,recursive call to 
            # function 'iterateDictIssues'.
            iterateDictIssues(fieldsDict, listInner)

        # If key is 'reporter',get its value,
        # to fetch the 'reporter name' of issue.
        elif (key == "reporter"):

            # Since type of object is Json str 
            # convert to dictionary object.
            reporterDict = dict(values)

            # The 'displayName', we want,is present
            # in,further, nested dictionary object.
            # Hence,recursive call to function 'iterateDictIssues'.
            iterateDictIssues(reporterDict, listInner)

        # Issue keyID 'key' is directly accessible.
        # Get the value of key "key" and append
        # to temporary list object.
        elif(key == 'key'):
            keyIssue = values
            listInner.append(keyIssue)

        # Get the value of key "summary",and,
        # append to temporary list object, once matched.
        elif(key == 'summary'):
            keySummary = values
            listInner.append(keySummary)

        # Get the value of key "displayName",and,
        # append to temporary list object,once matched.
        elif(key == "displayName"):
            keyReporter = values
            listInner.append(keyReporter)

# Iterate through the API output and look
# for key 'issues'.
for key, value in dictProjectIssues.items():

    # Issues fetched, are present as list elements,
    # against the key "issues".
    if(key == "issues"):

        # Get the total number of issues present
        # for our project.
        totalIssues = len(value)

        # Iterate through each issue,and,
        # extract needed details-Key, Summary,
        # Reporter Name.
        for eachIssue in range(totalIssues):
            listInner = []

            # Issues related data,is nested 
            # dictionary object.
            iterateDictIssues(value[eachIssue], listInner)

            # We append, the temporary list fields,
            # to a final list.
            listAllIssues.append(listInner)

# Prepare a dataframe object,with the final 
# list of values fetched.
dfIssues = pd.DataFrame(listAllIssues, columns=["Reporter",
                                                "Summary",
                                                "Key"])

# Reframing the columns to get proper 
# sequence in output.
columnTiles = ["Key", "Summary", "Reporter"]
dfIssues = dfIssues.reindex(columns=columnTiles)
print(dfIssues)
```

**输出:**

![](img/a9008b049e5fc391d131da9b5fe73bde.png)

在 python 代码中使用 JIRA REST API 从 JIRA 工具收到的问题