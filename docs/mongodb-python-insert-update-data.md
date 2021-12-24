# MongoDB Python |插入和更新数据

> 原文:[https://www . geesforgeks . org/MongoDB-python-insert-update-data/](https://www.geeksforgeeks.org/mongodb-python-insert-update-data/)

**先决条件:** [MongoDB Python 基础知识](https://www.geeksforgeeks.org/mongodb-and-python/)
我们将首先了解如何在数据库集合中插入文档/条目。然后，我们将研究如何使用 python 中的 pymongo 库更新 MongoDB 中的现有文档。更新命令帮助我们更新已经插入到 MongoDB 数据库集合中的查询数据。

**插入数据**

我们将首先在 MongoDB 中插入数据。

*   **Step 1 – Establishing Connection**: Port number Default: 27017

    ```
    conn = MongoClient(‘localhost’, port-number)
    ```

    如果使用默认端口号，即 27017。替代连接方法:

    ```
    conn = MongoClient()
    ```

*   **Step 2 – Create Database or Switch to Existing Database:**

    ```
    db = conn.dabasename
    ```

    创建集合或切换到现有集合:

    ```
    collection = db.collection_name
    ```

*   **Step 3 – Insert :** To Insert Data create a dictionary object and insert data in database. Method used to insert data:

    ```
     insert_one() or insert_many()
    ```

    在插入之后，我们使用 find()命令来查找集合中的文档。find()方法发出查询以从 MongoDB 中的集合中检索数据。MongoDB 中的所有查询都有一个集合的范围。
    注意:ObjectId 对于数据库集合中的每个条目都是不同的。
    让我们借助代码来理解数据插入:-

    ```
    # Python code to illustrate
    # inserting data in MongoDB
    from pymongo import MongoClient

    try:
        conn = MongoClient()
        print("Connected successfully!!!")
    except:  
        print("Could not connect to MongoDB")

    # database
    db = conn.database

    # Created or Switched to collection names: my_gfg_collection
    collection = db.my_gfg_collection

    emp_rec1 = {
            "name":"Mr.Geek",
            "eid":24,
            "location":"delhi"
            }
    emp_rec2 = {
            "name":"Mr.Shaurya",
            "eid":14,
            "location":"delhi"
            }

    # Insert Data
    rec_id1 = collection.insert_one(emp_rec1)
    rec_id2 = collection.insert_one(emp_rec2)

    print("Data inserted with record ids",rec_id1," ",rec_id2)

    # Printing the data inserted
    cursor = collection.find()
    for record in cursor:
        print(record)
    ```

    输出:

    ```
    Connected successfully!!!
    Data inserted with record ids    
    {'_id': ObjectId('5a02227b37b8552becf5ed2a'), 
    'name': 'Mr.Geek', 'eid': 24, 'location': 'delhi'}
    {'_id': ObjectId('5a02227c37b8552becf5ed2b'), 'name':
    'Mr.Shaurya', 'eid': 14, 'location': 'delhi'}

    ```

**更新 MongoD** B 中的数据

**使用的方法:update_one()和 update _ multi()**
**传递的参数:**
+一个匹配要更新的文档的过滤器文档
+一个指定要执行的修改的更新文档
+一个可选的 upsert 参数

在 MongoDB 中插入数据后，让我们更新 id 为:24 的员工的数据

```
# Python code to illustrate
# updating data in MongoDB
# with Data of employee with id:24
from pymongo import MongoClient

try:
    conn = MongoClient()
    print("Connected successfully!!!")
except:  
    print("Could not connect to MongoDB")

# database
db = conn.database

# Created or Switched to collection names: my_gfg_collection
collection = db.my_gfg_collection

# update all the employee data whose eid is 24
result = collection.update_many(
        {"eid":24},
        {
                "$set":{
                        "name":"Mr.Geeksforgeeks"
                        },
                "$currentDate":{"lastModified":True}

                }
        )

print("Data updated with id",result)

# Print the new record
cursor = collection.find()
for record in cursor:
    print(record)
```

输出:

```
Connected successfully!!!
Data updated with id 
{'_id': ObjectId('5a02227b37b8552becf5ed2a'), 
'name': 'Mr.Geeksforgeeks', 'eid': 24, 'location': 
'delhi', 'lastModified': datetime.datetime(2017, 11, 7, 21, 19, 9, 698000)}
{'_id': ObjectId('5a02227c37b8552becf5ed2b'), 'name': 
'Mr.Shaurya', 'eid': 14, 'location': 'delhi'}

```

要查找集合中更新的文档或条目数，请使用。

```
 print(result.matched_count) 
```

这里的输出是 1。