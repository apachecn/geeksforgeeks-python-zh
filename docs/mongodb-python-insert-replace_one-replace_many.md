# MongoDB Python–插入和替换操作

> 原文:[https://www . geesforgeks . org/MongoDB-python-insert-replace _ one-replace _ multi/](https://www.geeksforgeeks.org/mongodb-python-insert-replace_one-replace_many/)

**先决条件:** [MongoDB Python 基础知识](https://www.geeksforgeeks.org/mongodb-and-python/)
本文主要讨论如何替换集合中的文档或条目。我们只能替换已经插入数据库的数据。
**使用的方法:**替换一个()和替换多个()
目的:用新文档替换旧文档的全部数据

**插入蒙古数据库**

我们将首先在 MongoDB 中插入数据。

```
# Python code to illustrate
# Insert in MongoDB
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

# Printing the data inserted
cursor = collection.find()
for record in cursor:
    print(record)
```

输出:

```
Connected successfully!!!
Data inserted with record ids    
{'_id': ObjectId('5a02227b37b8552becf5ed2a'), 'name': 
'Mr.Geek', 'eid': 24, 'location': 'delhi'}
{'_id': ObjectId('5a02227c37b8552becf5ed2b'), 'name': 
'Mr.Shaurya', 'eid': 14, 'location': 'delhi'}
{'_id': ObjectId('5a02227c37b8552becf5ed2c'), 'name': 
'Mr.Coder', 'eid': 14, 'location': 'gurugram'}

```

**替换 _one()**

插入数据后，让我们替换姓名为沙尔亚先生的员工的数据

```
# Python code to illustrate 
# Replace_one() in MongoDB
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

# replace one of the employee data whose name is Mr.Shaurya
result = collection.replace_one(
        {"name":"Mr.Shaurya"},
        {
                "name":"Mr.GfG",
                "eid":45,
                "location":"noida"

                }
        )

print("Data replaced with id",result)

# Print the new record
cursor = collection.find()
for record in cursor:
    print(record)
```

```
Connected successfully!!!
Data replaced with id 
{'_id': ObjectId('5a02227b37b8552becf5ed2a'), 'name': 
'Mr.Geek', 'eid': 24, 'location': 'delhi'}
{'_id': ObjectId('5a02227c37b8552becf5ed2b'), 'name': 
'Mr.GfG', 'eid': 45, 'location': 'noida'}
{'_id': ObjectId('5a02227c37b8552becf5ed2c'), 'name': 
'Mr.Coder', 'eid': 14, 'location': 'gurugram'}

```

我们已成功替换了员工姓名为“Shaurya 先生”的文档，并用新的姓名为“GfG 先生”(目前)的文档替换了整个文档。

**替换 _ 多()**

*考虑数据与插入时相同。*
将所有数据条目替换为 eid:14。

```
# Python code to illustrate 
# Replace_many() in MongoDB
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

# replace one of the employee data whose name is Mr.Shaurya
result = collection.replace_many(
        {"eid":14},
        {
                "name":"Mr.GfG",
                "eid":45,
                "location":"noida"

                }
        )

print("Data replaced with id",result)

# Print the new record
cursor = collection.find()
for record in cursor:
    print(record)
```

输出应该是:

```
Connected successfully!!!
Data replaced with id 
{'_id': ObjectId('5a02227b37b8552becf5ed2a'), 'name': 
'Mr.Geek', 'eid': 24, 'location': 'delhi'}
{'_id': ObjectId('5a02227c37b8552becf5ed2b'), 'name': 
'Mr.GfG', 'eid': 45, 'location': 'noida'}
{'_id': ObjectId('5a02227c37b8552becf5ed2c'), 'name': 
'Mr.GfG', 'eid': 45, 'location': 'noida'}

```

这里我们可以看到 eid:14 的两个条目都被新数据替换了。(即使数据相同，ObjectId 也会不同)。