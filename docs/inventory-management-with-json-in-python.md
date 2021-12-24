# 用 Python 中的 JSON 进行库存管理

> 原文:[https://www . geesforgeks . org/inventory-management-with-JSON-in-python/](https://www.geeksforgeeks.org/inventory-management-with-json-in-python/)

库存管理系统用于管理商店产品和跟踪所有商品库存，我们还可以使用它来检查商店的购买历史。基本上，我们正在开发一个系统，通过使用计算机来管理/自动化任何零售店的一些过程。因此，通过使用该系统，我们可以记录产品的数据，甚至所有发生在店内的购买。

因此，在这里，我们将使用 python 开发一个库存管理系统，为了存储数据，我们将使用 JSON 文件。首先，我们将使用 python 代码本身创建示例数据，然后逐个开发所有函数。

我们必须在每个函数上打开 JSON 文件，并以 python 字典格式加载 JSON 数据，然后再次将字典数据转换回 JSON 格式，然后关闭文件。

### 创建数据并添加到 JSON 文件:

让我们在 Python 字典中生成数据。

## 蟒蛇 3

```py
import json

# Creating Dictionary to store data
available_products = {1001: {"name": "avacado", "price": 230,
                             "category": "grocery",
                             "quantity": 10, "date": "10/03/2021"},
                      1002: {"name": "lotion", "price": 250,
                             "category": "beauty & personal",
                             "quantity": 100,
                             "date": "15/07/2021"},
                      1003: {"name": "pain reliever", "price": 500,
                             "category": "health",
                             "quantity": 200, "date": "12/04/2021"},
                      1004: {"name": "dry pasta", "price": 20,
                             "category": "grocery",
                             "quantity": 50, "date": "27/06/2021"},
                      1005: {"name": "toothbrush", "price": 700,
                             "category": "beauty & personal",
                             "quantity": 100,
                             "date": "30/01/2021"},
                      1006: {"name": "halloween candy", "price": 33,
                             "category": "grocery",
                             "quantity": 56, "date": "22/02/2021"},
                      1007: {"name": "mascara", "price": 765,
                             "category": "beauty & personal",
                             "quantity": 70,
                             "date": "11/03/2021"},
                      1008: {"name": "capsicum", "price": 764,
                             "category": "grocery",
                             "quantity": 90, "date": "16/02/2021"},
                      1009: {"name": "blush", "price": 87,
                             "category": "beauty & personal",
                             "quantity": 50, "date": "17/07/2021"},
                      1010: {"name": "granola bars", "price": 24,
                             "category": "grocery", "quantity": 60,
                             "date": "20/05/2021"},
                      }

# Formatting Dictionary into JSON format
js = json.dumps(available_products)
''' json.dumps() function converts a Python object into a json string '''
js  # so we got all data in json string format here

# Create Jason File for DataBase and Write data Into File
fd = open("data.json", 'w')

fd.write(js)  # writing string into file
fd.close()  # Close File After Inserting Data
```

因此，我们已经为我们的库存管理系统创建了数据，现在我们必须创建函数来访问这些数据，并在其上处理各种功能。

## 所以对于这个系统，我们将添加两个主要部分

*   管理级功能。(用于系统管理员操作)
*   用户级功能。(将由客户使用)

## 管理级功能

基本上，这只是为了管理一个拥有额外权限(如插入、更新和删除产品详细信息)的人的库存，这些权限只应在所有者或经理级别。

以下功能将有助于管理功能之间的协调

## 蟒蛇 3

```py
def admin():
    print("============= Welcome to the Admin Inventory Management System =====")

    while (1):
        print("1)Display DataBase/All Products with there details")
        print("2)Display Specific Product with its details")
        print("3)Insert Data Into DataBase")
        print("4)Update Product in Database")
        print("5)Delete Product in DataBase")
        print("6)Display User Purchase Reports")
        print("7)Exit")
        print("Enter Your Choice :- ")

        n = int(input())
        if (n == 1):
            display_data()
        elif (n == 2):
            display_specific_data()
        elif (n == 3):
            add_new()
        elif (n == 4):
            update_prod_data()
        elif (n == 5):
            delete_prod()
        elif (n == 6):
            display_reports_admin()
        elif (n == 7):
            break
        else:
            print("Invalid Choice...!!!")
```

该级别将提供以下功能

### 1.显示库存中所有产品的功能

在这个功能中，管理员将有两个选项，要么他想要数据库中的所有列表，要么他想要查看所有产品的类别。

注意:为了使表格格式看起来更好，我们将使用熊猫。

## 蟒蛇 3

```py
def display_data():
    import pandas as pd
    import json
    fd = open("data.json", 'r')  # Open file in read mode
    txt = fd.read()  # reading data from file
    data = json.loads(txt)

    # This will parse the JSON data,
    # populates a Python dictionary with the data
    fd.close()
    print("Enter '0' To Display Data Category Wise or '1' \
    To Show Data As its Sequence Of Insertion :- ")
    n = int(input())

    # Display All Records
    if (n == 1):
        table = pd.DataFrame(
            columns=['ID', 'name', 'price', 'category',
                     'quantity', 'date'])

        # Creating Pandas dataframe to show data in table
        # format later
        for i in data.keys():
            '''Fetch all keys in dictionary'''
            temp = pd.DataFrame(columns=['ID'])
            temp['ID'] = [i]

            for j in data[i].keys():
                temp[j] = [data[i][j]]
            table = table.append(temp)
        table = table.reset_index(drop=True)

        # This will reset index of dataframe
        from IPython.display import display
        display(table)
    elif (n == 0):

        # Display Records by Category
        table = pd.DataFrame(
            columns=['ID', 'name', 'price', 'category',
                     'quantity', 'date'])
        cat = []

        for i in data.keys():
            temp = pd.DataFrame(columns=['ID'])
            temp['ID'] = [i]
            for j in data[i].keys():
                temp[j] = [data[i][j]]
                if (j == 'category'):
                    cat.append(data[i][j])
            table = table.append(temp)
            table = table.reset_index(drop=True)
            cat = set(cat)
            cat = list(cat)

        for k in cat:
            temp = pd.DataFrame()
            temp = table[table['category'] == k]
            print("Data Of Products Of Category "+k+" is:- ")
            from IPython.display import display
            display(temp)
    else:
        print("Enter Valid Choice...!!!")

# display_data() # Uncomment This Line To Run This Function
# Note :- Ensure You Have data.json File to Fetch Data
```

### 2.显示特定产品详细信息的功能:

在此功能中，管理员必须输入产品的产品标识，以查看他想要检查的详细信息。他将获得该特定产品的所有详细信息。

## 蟒蛇 3

```py
def display_specific_data():
    import pandas as pd
    import json
    fd = open("data.json", 'r')
    txt = fd.read()
    data = json.loads(txt)
    fd.close()
    print("Enter Product ID Whoes Details You Want to Have a Look on :- ")
    i = input()

    # Following Code will Filter out Product ID from Records
    if i in data.keys():
        temp = pd.DataFrame(columns=['ID'])
        temp['ID'] = [i]

        for j in data[i].keys():
            temp[j] = [data[i][j]]

        from IPython.display import display
        display(temp)
    else:
        print("You Have Entered Wrong Product ID \
        that is not Present in DataBase...!!!")

# display_specific_data() # Uncomment This Line To Run This Function
# Note :- Ensure You Have data.json File to Fetch Data
```

### 3.插入功能在库存中添加新产品:

此功能将允许管理员在库存中添加新产品详细信息。如果管理员想要添加除基本属性/详细信息之外的其他属性/详细信息，还提供了为特定产品添加新属性属性的功能。

**注意:**这里的程序对我们插入的数据更加具体，我们可以进行更改，使其适用于所有类型

## 蟒蛇 3

```py
def add_new():
    import json
    fd = open("data.json", 'r')
    txt = fd.read()
    data = json.loads(txt)
    fd.close()
    print("Enter New Product ID :- ")
    id = input()

    if id not in data.keys():
        print("Enter Product Name :- ")
        name = input()

        print("Enter Price of Product(price for product quantity as 1) :- ")
        price = input()

        print("Enter Category of Product :- ")
        category = input()

        print("Enter Quantity of Product :- ")
        quantity = input()

        print("Enter The Date on Which Product is Added in Inventory :- ")
        date = input()

        data[id] = {'name': name, 'price': price,
                    'category': category, 'quantity': quantity, 'date': date}
        print("Please Press '0' to Add New Attributes\
        /Properties of Product or Press '1' to Continue :- ")
        z = int(input())

        if(z == 0):
            print("Enter Number of New Attributes/Properties of Product :- ")
            n = int(input())

            for i in range(n):
                print("Enter Attribute Name That you Want To Add :- ")
                nam = input()
                print("Enter The "+str(nam)+" of Product :- ")
                pro = input()
                data[id][nam] = pro
        print("Product ID "+str(id)+" Added Successfully...!!!")

    else:
        print("The Product ID you Have Entered Is Already Present\
        t in DataBase Please Check...!!!")
    js = json.dumps(data)
    fd = open("data.json", 'w')
    fd.write(js)
    fd.close()

# add_new() # Uncomment This Line To Run This Function
# Note :- Ensure You Have data.json File to Fetch Data
```

### 4.删除库存中的产品:

在这里，管理员可以删除缺货或想要删除的产品。此外，它还会在无效的产品标识上抛出一个错误。

## 蟒蛇 3

```py
def delete_prod():
    import json
    fd = open("data.json", 'r')
    txt = fd.read()
    data = json.loads(txt)
    fd.close()
    print("Enter The Product ID of The Product Which You Want To Delete :- ")
    temp = input()

    if temp in data.keys():

          # here we are removing that particular data
        data.pop(temp) 
        print("Product ID "+str(temp)+" Deleted Successfully...!!!")
    else:
        print("Invalid Product ID...!!!")
    js = json.dumps(data)
    fd = open("data.json", 'w')
    fd.write(js)
    fd.close()

# delete_prod() # Uncomment This Line To Run This Function
# Note :- Ensure You Have data.json File to Fetch Data
```

### 5.更新产品数据:

该功能将为管理员提供两个选项，要么他想要更新产品的所有细节，要么他想要编辑产品的任何特定细节/属性。此外，它还会在无效的产品标识上抛出一个错误。

## 蟒蛇 3

```py
def update_prod_data():
    import json
    fd = open("data.json", 'r')
    txt = fd.read()
    data = json.loads(txt)
    fd.close()
    print("Enter The Product ID of The Product\
    Which You Want To Update :- ")
    temp = input()

    if temp in data.keys():
        print("Want to update whole product data\
        press '0' else '1' for specific data :- ")
        q = int(input())
        if (q == 0):

            print("Enter Product Name :- ")
            name = input()

            print("Enter Price of Product(price for product quantity as 1) :- ")
            price = input()

            print("Enter Category of Product :- ")
            category = input()

            print("Enter Quantity of Product :- ")
            quantity = input()

            print("Enter The Date on Which Product is Added in Inventory :- ")
            date = input()

            data[temp] = {'name': name, 'price': price,
                          'category': category, 'quantity': quantity,
                          'date': date}
            print(
                "Please Press '0' to Add more Attributes\
                /Properties of Product or Press '1' to Continue :- ")
            z = int(input())
            if(z == 0):
                print("Enter Number of New Attributes/Properties of Product :- ")
                n = int(input())

                for i in range(n):
                    print("Enter Attribute Name That you Want To Add :- ")
                    nam = input()
                    print("Enter The "+str(nam)+" of Product :- ")
                    pro = input()
                    data[temp][nam] = pro
            print("Product ID "+str(temp)+" Updated Successfully...!!!")

        elif(q == 1):
            print("Enter Which Attribute of Product You want to Update :- ")
            p = input()

            if p in data[temp].keys():
                print("Enter "+str(p)+" of Product :- ")
                u = input()
                data[temp][p] = u
                print("Product ID "+str(temp)+"'s attribute " +
                      str(p)+" is Updated Successfully...!!!")
            else:
                print("Invalid Product Attribute...!!!")
        else:
            print("Invalid Choice...!!!")
    else:
        print("Invalid Product ID...!!!")
    js = json.dumps(data)
    fd = open("data.json", 'w')
    fd.write(js)
    fd.close()

# update_prod_data() # Uncomment This Line To Run This Function
# Note :- Ensure You Have data.json File to Fetch Data
```

### 6.向管理员显示用户购买报告:

管理员可以通过两个选项查看用户的购买情况，比如他想查看所有购买报告，或者想查看任何特定客户/用户的购买报告。这还提供了一种功能，可以显示一条消息:如果任何用户没有购买，则不显示任何报告。此外，它还会在无效的用户标识上抛出一个错误。

## 蟒蛇 3

```py
def display_reports_admin():
    import os.path
    import pandas as pd
    import json
    if (os.path.isfile("user_data.json") is False):

        # Check for if file is present or not
        # File will be generated only
        # if any user will do some purchase
        print("No User Reports are Present")
        return

    fd = open("user_data.json", 'r')
    txt = fd.read()
    user_data = json.loads(txt)
    fd.close()
    print("Enter '0' to Check All Bills/Reports and \
    '1' To Check Specific User Bills/Reports :- ")
    n = int(input())

    if (n == 1):
        print("Enter User ID Whoes Details You Want to Have a Look on")
        i = input()
        temp = pd.DataFrame()

        if i in user_data.keys():
            for j in user_data[i].keys():
                d = dict()
                d['User ID'] = i
                d['Purchase Number'] = j
                for k in user_data[i][j].keys():
                    d[k] = user_data[i][j][k]
                temp = temp.append(d, ignore_index=True)
                d = dict()
            temp = temp.reset_index(drop=True)

            from IPython.display import display
            display(temp)

        else:
            print("You Have Entered Wrong User ID that is not Present in DataBase...!!!")
    elif (n == 0):
        table = pd.DataFrame()

        for i in user_data.keys():
            temp = pd.DataFrame()

            for j in user_data[i].keys():
                d = dict()
                d['User ID'] = i
                d['Purchase Number'] = j

                for k in user_data[i][j].keys():
                    d[k] = user_data[i][j][k]
                temp = temp.append(d, ignore_index=True)
                d = dict()
            table = table.append(temp)
        table = table.reset_index(drop=True)
        from IPython.display import display
        display(table)
    else:
        print("Please Enter Valid Choice...!!!")

# display_reports_admin() # Uncomment This Line To Run This Function
# Note :- Ensure You Have data.json File to Fetch Data
```

### 7.删除整个数据库(删除整个库存记录):

管理员也可以删除整个数据库，如果他想清除它。

## 蟒蛇 3

```py
def delete_all():
    fd = open("data.json", 'r')
    txt = fd.read()
    data = json.loads(txt)
    fd.close()
    data = {}  # Replacing Data with NULL Dictionary
    js = json.dumps(data)
    fd = open("data.json", 'w')
    fd.write(js)
    fd.close()
```

## 用户级功能:

这基本上类似于客户可以操作来购买产品并获得他的账单，并且以前的账单记录也没有功能或对产品的访问权限来插入、修改或删除它。

以下功能将有助于管理功能之间的协调

## 蟒蛇 3

```py
def user():
    print("===============\
    Welcome to the User Inventory Management System\
    ===============================================")

    while (1):
        print("1)Display All Products With Details")
        print("2)Display Specific Product With Details")
        print("3)Display All Purchase Bills")
        print("4)Buy The Product")
        print("5)Exit")
        print("Enter Your Choice :- ")
        n = int(input())
        if (n == 1):
            display_data()
        elif (n == 2):
            display_specific_data()
        elif (n == 3):
            display_user_data()
        elif (n == 4):
            buy_product()
        elif (n == 5):
            break
        else:
            print("Invalid Choice...!!!")
```

以下是用户级别的功能

**注意:**在用户购买商品之前，我们应该向他展示库存中所有可用产品的列表，这样我们就可以使用为 admin 创建的相同功能来显示产品。

### 1.显示用户购买报告:

该功能将帮助用户跟踪他的购买情况和直到今天的所有账单报告。此外，如果用户输入用户标识，此功能仅向用户提供信息。(我们也可以在这里添加密码功能，以增加更多功能)

## 蟒蛇 3

```py
def display_user_data():
    import os.path
    import json

    if (os.path.isfile("user_data.json") is False):
        print("No User Reports are Present")
        return

    fd = open("user_data.json", 'r')
    txt = fd.read()
    user_data = json.loads(txt)
    fd.close()
    print("Enter your User ID to Display All your Bills :- ")
    i = input()
    temp = pd.DataFrame()

    if i in user_data.keys():
        for j in user_data[i].keys():
            d = dict()
            d['User ID'] = i
            d['Purchase Number'] = j
            for k in user_data[i][j].keys():
                d[k] = user_data[i][j][k]
            temp = temp.append(d, ignore_index=True)
            d = dict()
        temp = temp.reset_index(drop=True)

        from IPython.display import display
        display(temp)
    else:
        print("You Have Entered Wrong User ID that is not Present in DataBase...!!!")
```

### 2.创建账单的功能:

用户/客户将在购买后立即收到他的账单，账单上有一个唯一的 10 位交易标识。如果一个用户一次购买多种产品，它会给出一个总账单。

## 蟒蛇 3

```py
def generate_bill(user_id, prod_id, price, time_date,
                  purchase_no, name, category,
                  quantity_all, transaction_id):
    print("================================\
  ================= Bill ================\
  =================================")
    print("########################################")
    print("   User ID :-", user_id)
    print("############################################")
    amount = 0
    n = len(purchase_no)

    for i in range(n):
        print("--------------------------------------")
        amount = amount+float(price[i])*float(quantity_all[i])
        print("Purchase number", purchase_no[i],
              "\nPurchase Time :-", time_date[i],
              "\nProduct ID :-", prod_id[i],
              "\nName Of Product :-",
              name[i], "\nCategory Of Product :-", category[i],
              "\nPrice of Product per Item :-", price[i],
              "\nPurchase Quantity :-", quantity_all[i])
        print("-------------------------------------------------")
    print("*********************************************************")
    print("      Total Payable Bill :-",
          amount, "Transaction ID :-", transaction_id)
    print("*************************************")
```

### 3.为用户购买产品的功能:

这是这一部分的主要功能，这将允许用户/客户购买产品。如果客户购买的产品数量高于库存数量，这将会产生错误。如果用户希望节省精力或重新启动流程，也可以跳过该产品，他还将获得一次更正数量的机会。此外，如果产品不在库存中(数量=0)，客户将收到缺货消息。客户可以通过使用产品标识同时购买多个产品(我们也可以通过产品名称添加购买产品)如果用户/客户输入错误的选择，他将收到错误消息。

## 蟒蛇 3

```py
def buy_product():
    import time
    import random
    import os.path

    if (os.path.isfile("user_data.json") is False):
        user_data = {}
    else:
        fd = open("user_data.json", 'r')
        txt = fd.read()
        user_data = json.loads(txt)
        fd.close()

    fd = open("data.json", 'r')
    txt = fd.read()
    data = json.loads(txt)
    fd.close()
    print("Enter Your User ID if You are Old Customer\
    else press '0' To New User ID :- ")
    p = int(input())

    if (p == 0):
        if (len(user_data.keys()) == 0):
            user_id = 1000
        else:
            user_id = int(list(user_data.keys())[-1])+1
    else:
        if str(p) in user_data.keys():
            user_id = p
        else:
            user_id = -1

    if (user_id != -1):
        user_id = str(user_id)
        price = []
        time_date = []
        purchase_no = []
        name = []
        category = []
        quantity_all = []
        prod_id = []
        transaction_id = ''.join(random.choice(
            '0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ') for i in range(10))
        print("Enter Number of Products You Want To Buy :- ")
        n = int(input())
        print("Enter Data As Follows :- ")

        if user_id not in user_data.keys():
            user_data[user_id] = {}
            g = 0
        else:
            g = int(list(user_data[user_id].keys())[-1])+1

        for i in range(n):
            print("Enter Product ID of Product " +
                  str(i+1)+" that you want to buy")
            id = input()

            if id in data.keys():
                user_data[user_id][str(i+1+g)] = {}
                user_data[user_id][str(i+1+g)]['time_date'] = str(time.ctime())
                time_date.append(str(time.ctime()))
                if(float(data[id]['quantity']) == 0):
                    print("Product You Want is Currenty Out Of Stock...!!!")
                    continue

                purchase_no.append(i+1+g)
                name.append(data[id]['name'])
                user_data[user_id][str(i+1+g)]['name'] = data[id]['name']
                prod_id.append(id)
                user_data[user_id][str(i+1+g)]['product_id'] = id
                category.append(data[id]['category'])
                user_data[user_id][str(
                    i+1+g)]['category'] = data[id]['category']
                print("For Product "+str(data[id]['name']) +
                      " Available Quantity is :- "+str(data[id]['quantity']))
                print("Enter Quantity of Product " +
                      str(i+1)+" that you want to buy")
                quantity = input()

                if (float(quantity) <= float(data[id]['quantity'])):
                    data[id]['quantity'] = str(
                        float(data[id]['quantity'])-float(quantity))
                    quantity_all.append(quantity)
                    user_data[user_id][str(i+1+g)]['quantity'] = str(quantity)
                    price.append(data[id]['price'])
                    user_data[user_id][str(i+1+g)]['price'] = data[id]['price']
                    user_data[user_id][str(
                        i+1+g)]['Transaction ID'] = str(transaction_id)
                else:
                    print(
                        "The Quantity You Have Asked is Quite High\
                        Than That is Available in Stock")
                    print(
                        "Did you Want To buy According to The Quantity\
                        Available in Stock then Enter '0' Else '1'\
                        to skip This Product")
                    key = int(input())

                    if (key == 0):
                        print("Enter Quantity of Product " +
                              str(i+1)+" that you want to buy")
                        quantity = intput()
                        if (float(quantity) <= float(data[id]['quantity'])):
                            data[id]['quantity'] = str(
                                float(data[id]['quantity'])-float(quantity))
                            quantity_all.append(quantity)
                            user_data[user_id][str(
                                i+1)]['quantity'] = str(quantity)
                            price.append(data[id]['price'])
                            user_data[user_id][str(
                                i+1)]['price'] = data[id]['price']
                            user_data[user_id][str(
                                i+1+g)]['Transaction ID'] = str(transaction_id)
                        else:
                            print("Invalid Operation Got Repeated...!!!")
                    elif (key == 1):
                        continue
                    else:
                        print("Invalid Choice...!!!")
            else:
                print("Invalid Product ID...!!!")
        if(len(purchase_no) != 0):
            generate_bill(user_id, prod_id, price, time_date, purchase_no,
                          name, category, quantity_all, transaction_id)
    else:
        print("User ID Doesn't Exists...!!!")
    js = json.dumps(data)
    fd = open("data.json", 'w')
    fd.write(js)
    fd.close()
    js = json.dumps(user_data)
    fd = open("user_data.json", 'w')
    fd.write(js)
    fd.close()
```

毕竟，我们必须管理用户和管理员级别的功能。所以，代码是这样的，

## 蟒蛇 3

```py
import json
import pandas as pd

while (1):
    print("Choose Any One of The Following :- ")
    print("1)Admin")
    print("2)User")
    print("3)Exit")
    print("Enter Your Choice Here :- ")
    n = int(input())
    if (n == 1):
        admin()
    elif (n == 2):
        user()
    elif (n == 3):
        break
    else:
        print("Invalid Choice...!!!")
```

这是所有完整的库存管理系统，具有管理和用户功能。

## 下面是完整的实现:

## 蟒蛇 3

```py
import pandas as pd
import json
import os.path
import time
import random

# Creating Dictionary to store data
available_products = {1001: {"name": "avacado", "price": 230,
                             "category": "grocery",
                             "quantity": 10, "date": "10/03/2021"},
                      1002: {"name": "lotion", "price": 250,
                             "category": "beauty & personal",
                             "quantity": 100,
                             "date": "15/07/2021"},
                      1003: {"name": "pain reliever", "price": 500,
                             "category": "health",
                             "quantity": 200, "date": "12/04/2021"},
                      1004: {"name": "dry pasta", "price": 20,
                             "category": "grocery",
                             "quantity": 50, "date": "27/06/2021"},
                      1005: {"name": "toothbrush", "price": 700,
                             "category": "beauty & personal",
                             "quantity": 100,
                             "date": "30/01/2021"},
                      1006: {"name": "halloween candy", "price": 33,
                             "category": "grocery",
                             "quantity": 56, "date": "22/02/2021"},
                      1007: {"name": "mascara", "price": 765,
                             "category": "beauty & personal",
                             "quantity": 70,
                             "date": "11/03/2021"},
                      1008: {"name": "capsicum", "price": 764,
                             "category": "grocery",
                             "quantity": 90, "date": "16/02/2021"},
                      1009: {"name": "blush", "price": 87,
                             "category": "beauty & personal",
                             "quantity": 50, "date": "17/07/2021"},
                      1010: {"name": "granola bars", "price": 24,
                             "category": "grocery", "quantity": 60,
                             "date": "20/05/2021"},
                      }

# Formatting Dictionary into JSON format
js = json.dumps(available_products)

#  json.dumps() function converts a
# Python object into a json string
js  # so we got all data in json string format here

# Create Jason File for DataBase and Write data Into File
fd = open("data.json", 'w')
# it will open file into write mode if file
# does not exists then it will create file too'''
fd.write(js)  # writing string into file
fd.close()  # Close File After Inserting Data

def admin():
    print("========\
    Welcome to the Admin Inventory Management System \
    ==============")
    while (1):
        print("1)Display DataBase/All Products with there details")
        print("2)Display Specific Product with its details")
        print("3)Insert Data Into DataBase")
        print("4)Update Product in Database")
        print("5)Delete Product in DataBase")
        print("6)Display User Purchase Reports")
        print("7)Exit")
        print("Enter Your Choice :- ")
        n = int(input())
        if (n == 1):
            display_data()
        elif (n == 2):
            display_specific_data()
        elif (n == 3):
            add_new()
        elif (n == 4):
            update_prod_data()
        elif (n == 5):
            delete_prod()
        elif (n == 6):
            display_reports_admin()
        elif (n == 7):
            break
        else:
            print("Invalid Choice...!!!")

def display_data():

    fd = open("data.json", 'r')
    txt = fd.read()  # reading data from file
    data = json.loads(txt)

    # This will parse the JSON data, populates a
    # Python dictionary with the data
    fd.close()
    print("Enter '0' To Display Data Category Wise or '1' \
    To Show Data As its Sequence Of Insertion :- ")
    n = int(input())

    # Display All Records
    if (n == 1):
        table = pd.DataFrame(
            columns=['ID', 'name', 'price', 'category', 'quantity', 'date'])

        # Creating Pandas dataframe to show data in table format later
        for i in data.keys():

            # Fetch all keys in dictionary
            temp = pd.DataFrame(columns=['ID'])
            temp['ID'] = [i]
            for j in data[i].keys():
                temp[j] = [data[i][j]]
            table = table.append(temp)
        table = table.reset_index(drop=True)
        '''This will reset index of dataframe'''
        from IPython.display import display
        display(table)

    elif (n == 0):

        # Display Records by Category
        table = pd.DataFrame(
            columns=['ID', 'name', 'price', 'category',
                     'quantity', 'date'])
        cat = []

        for i in data.keys():
            temp = pd.DataFrame(columns=['ID'])
            temp['ID'] = [i]
            for j in data[i].keys():
                temp[j] = [data[i][j]]
                if (j == 'category'):
                    cat.append(data[i][j])
            table = table.append(temp)
            table = table.reset_index(drop=True)
            cat = set(cat)
            cat = list(cat)

        for k in cat:
            temp = pd.DataFrame()
            temp = table[table['category'] == k]
            print("Data Of Products Of Category "+k+" is:- ")
            from IPython.display import display
            display(temp)
    else:
        print("Enter Valid Choice...!!!")

# display_data() # Uncomment This Line To Run This Function
def display_specific_data():
    fd = open("data.json", 'r')
    txt = fd.read()
    data = json.loads(txt)
    fd.close()
    print("Enter Product ID Whoes Details You Want to Have a Look on :- ")
    i = input()

    # Following Code will Filter out Product ID from Records
    if i in data.keys():
        temp = pd.DataFrame(columns=['ID'])
        temp['ID'] = [i]
        for j in data[i].keys():
            temp[j] = [data[i][j]]
        from IPython.display import display
        display(temp)
    else:
        print("You Have Entered Wrong Product ID\
        that is not Present in DataBase...!!!")

# display_specific_data() # Uncomment This Line To Run This Function
def add_new():
    fd = open("data.json", 'r')
    txt = fd.read()
    data = json.loads(txt)
    fd.close()
    print("Enter New Product ID :- ")
    id = input()

    if id not in data.keys():
        print("Enter Product Name :- ")
        name = input()
        print("Enter Price of Product(price for product quantity as 1) :- ")
        price = input()
        print("Enter Category of Product :- ")
        category = input()
        print("Enter Quantity of Product :- ")
        quantity = input()
        print("Enter The Date on Which Product is Added in Inventory :- ")
        date = input()
        data[id] = {'name': name, 'price': price,
                    'category': category, 'quantity': quantity, 'date': date}
        print("Please Press '0' to Add New\
        Attributes/Properties of Product or Press '1' to Continue :- ")
        z = int(input())
        if(z == 0):
            print("Enter Number of New Attributes/Properties of Product :- ")
            n = int(input())
            for i in range(n):
                print("Enter Attribute Name That you Want To Add :- ")
                nam = input()
                print("Enter The "+str(nam)+" of Product :- ")
                pro = input()
                data[id][nam] = pro
        print("Product ID "+str(id)+" Added Successfully...!!!")
    else:
        print("The Product ID you Have Entered Is\
        Already Present in DataBase Please Check...!!!")
    js = json.dumps(data)
    fd = open("data.json", 'w')
    fd.write(js)
    fd.close()

# add_new() # Uncomment This Line To Run This Function
def delete_prod():
    fd = open("data.json", 'r')
    txt = fd.read()
    data = json.loads(txt)
    fd.close()
    print("Enter The Product ID of The Product Which You Want To Delete :- ")
    temp = input()
    if temp in data.keys():
        data.pop(temp)  # here we are removing that particular data
        print("Product ID "+str(temp)+" Deleted Successfully...!!!")
    else:
        print("Invalid Product ID...!!!")
    js = json.dumps(data)
    fd = open("data.json", 'w')
    fd.write(js)
    fd.close()

# delete_prod() # Uncomment This Line To Run This Function
def update_prod_data():
    fd = open("data.json", 'r')
    txt = fd.read()
    data = json.loads(txt)
    fd.close()
    print("Enter The Product ID of The Product\
    Which You Want To Update :- ")
    temp = input()

    if temp in data.keys():
        print("Want to update whole product data\
        press '0' else '1' for specific data :- ")
        q = int(input())

        if (q == 0):
            print("Enter Product Name :- ")
            name = input()
            print("Enter Price of Product(price for\
            product quantity as 1) :- ")
            price = input()
            print("Enter Category of Product :- ")
            category = input()
            print("Enter Quantity of Product :- ")
            quantity = input()
            print("Enter The Date on Which Product\
            is Added in Inventory :- ")
            date = input()
            data[temp] = {'name': name, 'price': price,
                          'category': category, 'quantity': quantity,
                          'date': date}
            print(
                "Please Press '0' to Add more Attributes/Properties of Product or Press '1' to Continue :- ")
            z = int(input())

            if(z == 0):
                print("Enter Number of New Attributes/Properties of Product :- ")
                n = int(input())
                for i in range(n):
                    print("Enter Attribute Name That you Want To Add :- ")
                    nam = input()
                    print("Enter The "+str(nam)+" of Product :- ")
                    pro = input()
                    data[temp][nam] = pro
            print("Product ID "+str(temp)+" Updated Successfully...!!!")

        elif(q == 1):
            print("Enter Which Attribute of Product You want to Update :- ")
            p = input()

            if p in data[temp].keys():
                print("Enter "+str(p)+" of Product :- ")
                u = input()
                data[temp][p] = u
                print("Product ID "+str(temp)+"'s attribute " +
                      str(p)+" is Updated Successfully...!!!")
            else:
                print("Invalid Product Attribute...!!!")
        else:
            print("Invalid Choice...!!!")
    else:
        print("Invalid Product ID...!!!")
    js = json.dumps(data)
    fd = open("data.json", 'w')
    fd.write(js)
    fd.close()

# update_prod_data() # Uncomment This Line To Run This Function
def display_reports_admin():
    if (os.path.isfile("user_data.json") is False):
        # Check for if file is present or not
        # File will be generated only if any user will do some purchase
        print("No User Reports are Present")
        return
    fd = open("user_data.json", 'r')
    txt = fd.read()
    user_data = json.loads(txt)
    fd.close()
    print("Enter '0' to Check All Bills/Reports\
    and '1' To Check Specific User Bills/Reports :- ")
    n = int(input())
    if (n == 1):
        print("Enter User ID Whoes Details You Want to Have a Look on")
        i = input()
        temp = pd.DataFrame()
        if i in user_data.keys():
            for j in user_data[i].keys():
                d = dict()
                d['User ID'] = i
                d['Purchase Number'] = j
                for k in user_data[i][j].keys():
                    d[k] = user_data[i][j][k]
                temp = temp.append(d, ignore_index=True)
                d = dict()
            temp = temp.reset_index(drop=True)
            from IPython.display import display
            display(temp)
        else:
            print("You Have Entered Wrong User ID that is not Present in DataBase...!!!")
    elif (n == 0):
        table = pd.DataFrame()
        for i in user_data.keys():
            temp = pd.DataFrame()
            for j in user_data[i].keys():
                d = dict()
                d['User ID'] = i
                d['Purchase Number'] = j
                for k in user_data[i][j].keys():
                    d[k] = user_data[i][j][k]
                temp = temp.append(d, ignore_index=True)
                d = dict()
            table = table.append(temp)
        table = table.reset_index(drop=True)
        from IPython.display import display
        display(table)
    else:
        print("Please Enter Valid Choice...!!!")

# display_reports_admin() # Uncomment This Line To Run This Function
def delete_all():
    fd = open("data.json", 'r')
    txt = fd.read()
    data = json.loads(txt)
    fd.close()
    data = {}  # Replacing Data with NULL Dictionary
    js = json.dumps(data)
    fd = open("data.json", 'w')
    fd.write(js)
    fd.close()

def user():
    print("======= Welcome to the User Inventory Management System ====")
    while (1):
        print("1)Display All Products With Details")
        print("2)Display Specific Product With Details")
        print("3)Display All Purchase Bills")
        print("4)Buy The Product")
        print("5)Exit")
        print("Enter Your Choice :- ")
        n = int(input())
        if (n == 1):
            display_data()
        elif (n == 2):
            display_specific_data()
        elif (n == 3):
            display_user_data()
        elif (n == 4):
            buy_product()
        elif (n == 5):
            break
        else:
            print("Invalid Choice...!!!")

def display_user_data():

    if (os.path.isfile("user_data.json") is False):
        print("No User Reports are Present")
        return
    fd = open("user_data.json", 'r')
    txt = fd.read()
    user_data = json.loads(txt)
    fd.close()
    print("Enter your User ID to Display All your Bills :- ")
    i = input()
    temp = pd.DataFrame()

    if i in user_data.keys():
        for j in user_data[i].keys():
            d = dict()
            d['User ID'] = i
            d['Purchase Number'] = j
            for k in user_data[i][j].keys():
                d[k] = user_data[i][j][k]
            temp = temp.append(d, ignore_index=True)
            d = dict()
        temp = temp.reset_index(drop=True)
        from IPython.display import display
        display(temp)
    else:
        print("You Have Entered Wrong User ID that is not Present in DataBase...!!!")

def generate_bill(user_id, prod_id, price, time_date, purchase_no,
                  name, category, quantity_all, transaction_id):
    print("========= Bill ========")
    print("#######################")
    print("   User ID :-", user_id)
    print("#################")
    amount = 0
    n = len(purchase_no)

    for i in range(n):
        print("-----------------------------------------")
        amount = amount+float(price[i])*float(quantity_all[i])
        print("Purchase number", purchase_no[i],
              "\nPurchase Time :-", time_date[i], "\nProduct ID :-",
              prod_id[i], "\nName Of Product :-",
              name[i], "\nCategory Of Product :-", category[i],
              "\nPrice of Product per Item :-", price[i],
              "\nPurchase Quantity :-", quantity_all[i])
        print("-----------------------------------")
    print("*****************************************")
    print("   Total Payable Bill :-",
          amount, "Transaction ID :-", transaction_id)
    print("***************************************")

def buy_product():

    if (os.path.isfile("user_data.json") is False):
        user_data = {}
    else:
        fd = open("user_data.json", 'r')
        txt = fd.read()
        user_data = json.loads(txt)
        fd.close()
    fd = open("data.json", 'r')
    txt = fd.read()
    data = json.loads(txt)
    fd.close()
    print("Enter Your User ID if You are Old \
    Customer else press '0' To New User ID :- ")
    p = int(input())
    if (p == 0):
        if (len(user_data.keys()) == 0):
            user_id = 1000
        else:
            user_id = int(list(user_data.keys())[-1])+1
    else:
        if str(p) in user_data.keys():
            user_id = p
        else:
            user_id = -1
    if (user_id != -1):
        user_id = str(user_id)
        price = []
        time_date = []
        purchase_no = []
        name = []
        category = []
        quantity_all = []
        prod_id = []
        transaction_id = ''.join(random.choice(
            '0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ') for i in range(10))
        print("Enter Number of Products You Want To Buy :- ")
        n = int(input())
        print("Enter Data As Follows :- ")
        if user_id not in user_data.keys():
            user_data[user_id] = {}
            g = 0
        else:
            g = int(list(user_data[user_id].keys())[-1])+1
        for i in range(n):
            print("Enter Product ID of Product " +
                  str(i+1)+" that you want to buy")
            id = input()
            if id in data.keys():
                user_data[user_id][str(i+1+g)] = {}
                user_data[user_id][str(i+1+g)]['time_date'] = str(time.ctime())
                time_date.append(str(time.ctime()))
                if(float(data[id]['quantity']) == 0.0):
                    print("Product You Want is Currenty Out Of Stock...!!!")
                    continue
                purchase_no.append(i+1+g)
                name.append(data[id]['name'])
                user_data[user_id][str(i+1+g)]['name'] = data[id]['name']
                prod_id.append(id)
                user_data[user_id][str(i+1+g)]['product_id'] = id
                category.append(data[id]['category'])
                user_data[user_id][str(
                    i+1+g)]['category'] = data[id]['category']
                print("For Product "+str(data[id]['name']) +
                      " Available Quantity is :- "+str(data[id]['quantity']))
                print("Enter Quantity of Product " +
                      str(i+1)+" that you want to buy")
                quantity = input()
                if (float(quantity) <= float(data[id]['quantity'])):
                    data[id]['quantity'] = str(
                        float(data[id]['quantity'])-float(quantity))
                    quantity_all.append(quantity)
                    user_data[user_id][str(i+1+g)]['quantity'] = str(quantity)
                    price.append(data[id]['price'])
                    user_data[user_id][str(i+1+g)]['price'] = data[id]['price']
                    user_data[user_id][str(
                        i+1+g)]['Transaction ID'] = str(transaction_id)
                else:
                    print(
                        "The Quantity You Have Asked is Quite High Than\
                        That is Available in Stock")
                    print(
                        "Did you Want To buy According to The Quantity\
                        Available in Stock then Enter '0' Else '1'\
                        to skip This Product")
                    key = int(input())
                    if (key == 0):
                        print("Enter Quantity of Product " +
                              str(i+1)+" that you want to buy")
                        quantity = intput()
                        if (float(quantity) <= float(data[id]['quantity'])):
                            data[id]['quantity'] = str(
                                float(data[id]['quantity'])-float(quantity))
                            quantity_all.append(quantity)
                            user_data[user_id][str(
                                i+1)]['quantity'] = str(quantity)
                            price.append(data[id]['price'])
                            user_data[user_id][str(
                                i+1)]['price'] = data[id]['price']
                            user_data[user_id][str(
                                i+1+g)]['Transaction ID'] = str(transaction_id)
                        else:
                            print("Invalid Operation Got Repeated...!!!")
                    elif (key == 1):
                        continue
                    else:
                        print("Invalid Choice...!!!")
            else:
                print("Invalid Product ID...!!!")
        if(len(purchase_no) != 0):
            generate_bill(user_id, prod_id, price, time_date, purchase_no,
                          name, category, quantity_all, transaction_id)
    else:
        print("User ID Doesn't Exists...!!!")
    js = json.dumps(data)
    fd = open("data.json", 'w')
    fd.write(js)
    fd.close()
    js = json.dumps(user_data)
    fd = open("user_data.json", 'w')
    fd.write(js)
    fd.close()

while (1):
    print("Choose Any One of The Following :- ")
    print("1)Admin")
    print("2)User")
    print("3)Exit")
    print("Enter Your Choice Here :- ")
    n = int(input())
    if (n == 1):
        admin()
    elif (n == 2):
        user()
    elif (n == 3):
        break
    else:
        print("Invalid Choice...!!!")
```

**输出:**

<video class="wp-video-shortcode" id="video-696039-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20211011174755/20211011_173445.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20211011174755/20211011_173445.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20211011174755/20211011_173445.mp4)</video>