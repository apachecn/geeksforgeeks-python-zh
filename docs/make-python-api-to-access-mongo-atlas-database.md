# 制作 Python API 访问 Mongo 地图集数据库

> 原文:[https://www . geesforgeks . org/make-python-API-to-access-mongo-atlas-database/](https://www.geeksforgeeks.org/make-python-api-to-access-mongo-atlas-database/)

先决条件: [Python |使用 Flask](https://www.geeksforgeeks.org/python-build-a-rest-api-using-flask/) 构建 REST API

RESTful APIs 是管理应用程序后端的非常有用的工具。它可以用来定义体系结构，以及使用由应用编程接口管理的路由来管理应用程序的依赖关系。Flask 是一个流行的构建 web 应用程序的微型框架。

在本文中，我们将学习如何通过 MongoDB 制作一个连接到 MongoDB Atlas 数据库服务的 Flask RESTful API。在此之前，您必须使用您的电子邮件地址在 [MongoDB Atlas](https://account.mongodb.com/account/login) 上创建一个用户帐户。

完成初始设置后。请遵循以下步骤:

*   **第一步:**点击**【新项目】**按钮，制作新项目。为您的项目指定一个名称，并添加成员(如果有)到您想要授予项目访问权限的方式中。点击**“创建项目”**按钮创建项目。你的仪表板应该是这样的。

![](img/ca9b5207bee4daa7146836a2bd4ff8e5.png)

*   **第二步:**点击**【建立集群】**。从弹出窗口中选择**“共享集群”**。选择所需的设置。例如:AWS 云提供商和孟买地区。您将在云上获得 512 兆字节的空间来托管您的数据库。**创建集群**。你的仪表板会是这样的。

![](img/5622372acb7ba0e2f5d91972cebb2441.png)

*   **第三步:**现在，点击**【连接】**。它将打开一个对话框。按照所示说明进行操作。将您的 IP 地址添加到白名单中。这是可以访问数据库的 IP 地址列表。接下来，创建用于访问数据库的用户名和密码。现在，点击**【选择连接方式】**。
*   **第四步:**现在，在出现的新对话框中点击**【连接你的应用】**。在驱动程序下拉列表中选择**“Python”**，在版本下拉列表中选择**“3.6 或更高版本”**。复制下一行的链接。它看起来像:

```
mongodb+srv://admin:<password>@cluster0-pm5vp.mongodb.net/test?retryWrites=true&w=majority
```

*   **第五步:**你的用户名出现在链接中(这里是管理员)。**用该用户的密码替换<密码>。**

这是将您的 Python 应用编程接口连接到数据库的链接或网址。现在，通过单击仪表板上的**“集合”**选项卡创建一个示例数据库，并通过单击**“添加我自己的数据”**创建一个新数据库。给你一个数据库名和一个表名，然后创建一个新的数据库。

对于这个例子，我创建了一个名为**“示例”**的数据库和一个名为**“样本表”的表。**

下面的 python 代码使用 **pymongo** 链接到您的 MongoDB Atlas 数据库。

**注意:**请安装以下库来运行 flask API : **flask、pymongo、dnspython、flask_cors**

```
from flask import Flask
from flask_cors import CORS
import pymongo

# Replace your URL here. Don't forget to replace the password.
connection_url = 'mongodb+srv://admin:<password>@cluster0-pm5vp.mongodb.net/test?retryWrites=true&w=majority'
app = Flask(__name__)
client = pymongo.MongoClient(connection_url)

# Database
Database = client.get_database('Example')
# Table
SampleTable = Database.SampleTable

if __name__ == '__main__':
    app.run(debug=True)
```

这将在您的 [http://localhost/5000](http://localhost/5000) 上启动一个烧瓶服务器，该服务器将连接到您的 MongoDB 地图集数据库。成功执行后，控制台将类似于:

![](img/935f230cf107d7ffc4ea046fbb838a48.png)

现在，您可以在应用编程接口中创建路由，并定义与数据库交互的函数。下面给出了一个如何映射路由并使用它们来接收值和与数据库交互的示例。

*   **路由(路径，方法):i** 用于定义路径，通过该路径可以调用相应的函数。<某些数据>用于从路径中提取值。
    例如下面的 insert 函数，路径中包含<名称>、< id >，这意味着路径中“insert-one/”之后的值将存储到 name 中，之后的值将存储在 id 中。方法用于定义函数将接受的方法类型。你可以从[这里了解一下。](https://www.geeksforgeeks.org/http-request-methods-python-requests/)

*   **jsonify(对象):**用于从传递的对象中创建一个 [JSON](https://www.geeksforgeeks.org/javascript-json/) 对象。

*   **insert_one(对象):**用于将传递的对象插入到调用它的集合中。

*   **find_one(对象):**用于查找数据库中与参数中作为关键字传递的对象相匹配的对象。它将整个文档作为一个对象返回。此方法返回与传递的键值匹配的第一个对象。

*   **查找(对象):**用于查找与传递的键值匹配的所有对象。

*   **update_one(对象):**用于更新数据库中某个对象的值，该对象与某些传递的键值相匹配。

```
from flask import Flask, jsonify, request
from flask_cors import CORS
import pymongo

connection_url = 'mongodb+srv://admin:samplearticle@cluster0-pm5vp.mongodb.net/test?retryWrites=true&w=majority'
app = Flask(__name__)
client = pymongo.MongoClient(connection_url)

# Database
Database = client.get_database('Example')
# Table
SampleTable = Database.SampleTable

# To insert a single document into the database,
# insert_one() function is used
@app.route('/insert-one/<name>/<id>/', methods=['GET'])
def insertOne(name, id):
    queryObject = {
        'Name': name,
        'ID': id
    }
    query = SampleTable.insert_one(queryObject)
    return "Query inserted...!!!"

# To find the first document that matches a defined query,
# find_one function is used and the query to match is passed
# as an argument.
@app.route('/find-one/<argument>/<value>/', methods=['GET'])
def findOne(argument, value):
    queryObject = {argument: value}
    query = SampleTable.find_one(queryObject)
    query.pop('_id')
    return jsonify(query)

# To find all the entries/documents in a table/collection,
# find() function is used. If you want to find all the documents
# that matches a certain query, you can pass a queryObject as an
# argument.
@app.route('/find/', methods=['GET'])
def findAll():
    query = SampleTable.find()
    output = {}
    i = 0
    for x in query:
        output[i] = x
        output[i].pop('_id')
        i += 1
    return jsonify(output)

# To update a document in a collection, update_one()
# function is used. The queryObject to find the document is passed as
# the first argument, the corresponding updateObject is passed as the
# second argument under the '$set' index.
@app.route('/update/<key>/<value>/<element>/<updateValue>/', methods=['GET'])
def update(key, value, element, updateValue):
    queryObject = {key: value}
    updateObject = {element: updateValue}
    query = SampleTable.update_one(queryObject, {'$set': updateObject})
    if query.acknowledged:
        return "Update Successful"
    else:
        return "Update Unsuccessful"

if __name__ == '__main__':
    app.run(debug=True)
```

**输出:**上面的代码对于不同的 URL 请求有不同的响应。

*   **insert-one 请求:**http://127 . 0 . 0 . 1:5000/insert-one/chit rank/1/
    这将下面的对象插入到集合 SampleTable 中，并返回 Query Inserted！！!'插入文档后。
    {
    style="color:rgb(80，80，80)；背景色:rgb(255，255，255)；”>“名称”:“chitrank”，
    “ID”:“1”，
    }

![](img/8bb87fc48fd2333b4c01c31813337b56.png)

*   **find-one 请求:**http://127 . 0 . 0 . 1:5000/find-one/Name/chit rank/
    该请求将返回一个与 URL 中传递的值相匹配的对象。返回的对象将显示在浏览器窗口上。

![](img/f2382771449b95050c1b7d3fd9f72f50.png)

*   **查找请求:**http://127 . 0 . 0 . 1:5000/find/
    该请求将返回调用表中的所有对象。返回的对象将显示在浏览器窗口上。

![](img/a0b3f4609e83358b7fdfed2b6ef40767.png)

*   **更新-一个请求:**http://127 . 0 . 0 . 1:5000/update/ID/1/Name/geeks forgeeks/
    此请求将更新将前两个参数与后两个值匹配的对象。成功更新后将返回“更新成功”

![](img/29b4f91e163fc6e73bedbed4c501c6db.png)

这些是我在这里提到的一些基本操作。这些足以管理一个数据库。MongoDB 提供了广泛的操作，您可以从 [MongoDB 官方文档](https://docs.mongodb.com/manual/reference/operator/query/)中阅读