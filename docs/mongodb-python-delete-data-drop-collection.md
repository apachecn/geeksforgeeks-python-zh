# MongoDB python |删除数据并删除集合

> 原文:[https://www . geesforgeks . org/MongoDB-python-delete-data-drop-collection/](https://www.geeksforgeeks.org/mongodb-python-delete-data-drop-collection/)

**先决条件:** [蒙古数据库基础](https://www.geeksforgeeks.org/mongodb-getting-started/)[插入并更新](https://www.geeksforgeeks.org/mongodb-python-insert-update-data/)

**目的:**删除数据库中集合的条目/文档。假定集合的名称为“my_collection”。
**使用的方法:**删除 _ 一个()或删除 _ 多个()

*   **删除符合条件的所有文档:**以下操作删除符合指定条件的所有文档。

    ```
     result = my_collection.delete_many({"name": "Mr.Geek"})
    ```

*   **查看已删除的文档数量:**

    ```
     print(result.deleted_count)
    ```

*   **Remove All Documents :**
    **Method 1 :** Remove all documents using delete_many()

    ```
     result= my_collection.delete_many({})
    ```

    **方法 2 :** 使用 collection.remove()删除所有文档

    ```
     result = my_collection.remove() 
    ```

    删除的最佳方法是删除集合，以便数据索引也被删除，然后在插入的数据中创建一个新集合。

*   删除收藏:

    ```
    db.my_collection.drop()
    ```

我们首先在集合中插入一个文档，然后根据查询删除这些文档。

```
# Python program to illustrate 
# delete, drop and remove
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
emp_rec3 = {
        "name":"Mr.Coder",
        "eid":14,
        "location":"gurugram"
        } 

# Insert Data
rec_id1 = collection.insert_one(emp_rec1)
rec_id2 = collection.insert_one(emp_rec2)
rec_id3 = collection.insert_one(emp_rec3)
print("Data inserted with record ids",rec_id1," ",rec_id2,rec_id3)

# Printing the document before deletion
cursor = collection.find()
for record in cursor:
    print(record)

# Delete Document with name : Mr Coder
result = collection.delete_one({"name":"Mr.Coder"})

# If query would have been delete all entries with eid:14
# use this
# result = collection.delete_many("eid":14})

cursor = collection.find()
for record in cursor:
print(record)
```

```
OUTPUT (comment line denoted by #)

Connected successfully!!!
Data inserted with record ids     
#Data INSERT
{'_id': ObjectId('5a02227c37b8552becf5ed2b'), 'name': 
'Mr.GfG', 'eid': 45, 'location': 'noida'}
{'_id': ObjectId('5a0c734937b8551c1cd03349'), 'name': 
'Mr.Shaurya', 'eid': 14, 'location': 'delhi'}
{'_id': ObjectId('5a0c734937b8551c1cd0334a'), 'name': 
'Mr.Coder', 'eid': 14, 'location': 'gurugram'}
#Mr.Coder is deleted
{'_id': ObjectId('5a02227c37b8552becf5ed2b'), 'name': 
'Mr.GfG', 'eid': 45, 'location': 'noida'}
{'_id': ObjectId('5a0c734937b8551c1cd03349'), 'name': 
'Mr.Shaurya', 'eid': 14, 'location': 'delhi'}

```