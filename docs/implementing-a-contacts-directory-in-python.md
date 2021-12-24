# 在 Python 中实现联系人目录

> 原文:[https://www . geesforgeks . org/impering-a-contacts-directory-in-python/](https://www.geeksforgeeks.org/implementing-a-contacts-directory-in-python/)

我们的任务是实现一个智能手机目录，收集用户的联系数据，直到用户提示程序。联系人数据是指联系人的姓名、电话号码、出生日期、联系人所属的类别(朋友、家人、工作、其他)、电子邮件地址。用户可以在提到的数据标签中输入尽可能多的数据。如果某些标签仍然没有数据，请将其存储为无。姓名和号码是创建联系人的必备条件。对目录执行以下操作:插入、删除、搜索、显示。

**方法:**
我们使用了 2D 列表的概念，并在 Python3 中实现了同样的概念。本代码共使用 8 个功能，即:

*   **initial_phonebook() :** 第一个要运行的功能，它初始化 phonebook。
*   **菜单():**显示用户可用的选项，并返回输入的选项。
*   **add_contact() :** 它将新联系人添加到联系人目录中。
*   **remove_existing() :** 它从联系人目录中删除一个现有联系人。
*   **delete_all() :** 它从联系人目录中删除所有联系人。
*   **display_all() :** 显示联系人目录中的所有联系人。
*   **search_existing() :** 它将在联系人目录中搜索并显示一个现有联系人。
*   **谢谢():**

保持用户体验和用户界面，我们使代码变得简单、可读和交互。您可以选择也可以不选择下面描述的所有功能。请检查代码解决方案。

请尝试在您的 Python IDLE 上运行此代码，因为如果您在此处运行需要用户输入，可能会出现一些错误。您也可以在 GFG 打开 IDE 页面并在那里运行您的代码，而不是直接从代码片段运行。

## 蟒蛇 3

```py
# importing the module
import sys

# this function will be the first to run as soon as the main function executes
def initial_phonebook():
    rows, cols = int(input("Please enter initial number of contacts: ")), 5

    # We are collecting the initial number of contacts the user wants to have in the
    # phonebook already. User may also enter 0 if he doesn't wish to enter any.
    phone_book = []
    print(phone_book)
    for i in range(rows):
        print("\nEnter contact %d details in the following order (ONLY):" % (i+1))
        print("NOTE: * indicates mandatory fields")
        print("....................................................................")
        temp = []
        for j in range(cols):

        # We have taken the conditions for values of j only for the personalized fields
        # such as name, number, e-mail id, dob, category etc
            if j == 0:
                temp.append(str(input("Enter name*: ")))

                # We need to check if the user has left the name empty as its mentioned that
                # name & number are mandatory fields.
                # So implement a condition to check as below.
                if temp[j] == '' or temp[j] == ' ':
                    sys.exit(
                        "Name is a mandatory field. Process exiting due to blank field...")
                    # This will exit the process if a blank field is encountered.

            if j == 1:
                temp.append(int(input("Enter number*: ")))
                # We do not need to check if user has entered the number because int automatically
                # takes care of it. Int value cannot accept a blank as that counts as a string.
                # So process automatically exits without us using the sys package.

            if j == 2:
                temp.append(str(input("Enter e-mail address: ")))
                # Even if this field is left as blank, None will take the blank's place
                if temp[j] == '' or temp[j] == ' ':
                    temp[j] = None

            if j == 3:
                temp.append(str(input("Enter date of birth(dd/mm/yy): ")))
                # Whatever format the user enters dob in, it won't make a difference to the compiler
                # Only while searching the user will have to enter query exactly the same way as
                # he entered during the input so as to ensure accurate searches
                if temp[j] == '' or temp[j] == ' ':

                # Even if this field is left as blank, None will take the blank's place
                    temp[j] = None
            if j == 4:
                temp.append(
                    str(input("Enter category(Family/Friends/Work/Others): ")))
                # Even if this field is left as blank, None will take the blank's place
                if temp[j] == "" or temp[j] == ' ':
                    temp[j] = None

        phone_book.append(temp)
        # By this step we are appending a list temp into a list phone_book
        # That means phone_book is a 2-D array and temp is a 1-D array

    print(phone_book)
    return phone_book

def menu():
    # We created this simple menu function for
    # code reusability & also for an interactive console
    # Menu func will only execute when called
    print("********************************************************************")
    print("\t\t\tSMARTPHONE DIRECTORY", flush=False)
    print("********************************************************************")
    print("\tYou can now perform the following operations on this phonebook\n")
    print("1\. Add a new contact")
    print("2\. Remove an existing contact")
    print("3\. Delete all contacts")
    print("4\. Search for a contact")
    print("5\. Display all contacts")
    print("6\. Exit phonebook")

    # Out of the provided 6 choices, user needs to enter any 1 choice among the 6
    # We return the entered choice to the calling function wiz main in our case
    choice = int(input("Please enter your choice: "))

    return choice

def add_contact(pb):
    # Adding a contact is the easiest because all you need to do is:
    # append another list of details into the already existing list
    dip = []
    for i in range(len(pb[0])):
        if i == 0:
            dip.append(str(input("Enter name: ")))
        if i == 1:
            dip.append(int(input("Enter number: ")))
        if i == 2:
            dip.append(str(input("Enter e-mail address: ")))
        if i == 3:
            dip.append(str(input("Enter date of birth(dd/mm/yy): ")))
        if i == 4:
            dip.append(
                str(input("Enter category(Family/Friends/Work/Others): ")))
    pb.append(dip)
    # And once you modify the list, you return it to the calling function wiz main, here.
    return pb

def remove_existing(pb):
    # This function is to remove a contact's details from existing phonebook
    query = str(
        input("Please enter the name of the contact you wish to remove: "))
    # We'll collect name of the contact and search if it exists in our phonebook

    temp = 0
    # temp is a checking variable here. We assigned a value 0 to temp.

    for i in range(len(pb)):
        if query == pb[i][0]:
            temp += 1
            # Temp will be incremented & it won't be 0 anymore in this function's scope

            print(pb.pop(i))
            # The pop function removes entry at index i

            print("This query has now been removed")
            # printing a confirmation message after removal.
            # This ensures that removal was successful.
            # After removal we will return the modified phonebook to the calling function
            # which is main in our program

            return pb
    if temp == 0:
        # Now if at all any case matches temp should've incremented but if otherwise,
        # temp will remain 0 and that means the query does not exist in this phonebook
        print("Sorry, you have entered an invalid query.\
    Please recheck and try again later.")

        return pb

def delete_all(pb):
    # This function will simply delete all the entries in the phonebook pb
    # It will return an empty phonebook after clearing
    return pb.clear()

def search_existing(pb):
    # This function searches for an existing contact and displays the result
    choice = int(input("Enter search criteria\n\n\
    1\. Name\n2\. Number\n3\. Email-id\n4\. DOB\n5\. Category(Family/Friends/Work/Others)\
    \nPlease enter: "))
    # We're doing so just to ensure that the user experiences a customized search result

    temp = []
    check = -1

    if choice == 1:
    # This will execute for searches based on contact name
        query = str(
            input("Please enter the name of the contact you wish to search: "))
        for i in range(len(pb)):
            if query == pb[i][0]:
                check = i
                temp.append(pb[i])

    elif choice == 2:
    # This will execute for searches based on contact number
        query = int(
            input("Please enter the number of the contact you wish to search: "))
        for i in range(len(pb)):
            if query == pb[i][1]:
                check = i
                temp.append(pb[i])

    elif choice == 3:
    # This will execute for searches based on contact's e-mail address
        query = str(input("Please enter the e-mail ID\
        of the contact you wish to search: "))
        for i in range(len(pb)):
            if query == pb[i][2]:
                check = i
                temp.append(pb[i])

    elif choice == 4:
    # This will execute for searches based on contact''s date of birth
        query = str(input("Please enter the DOB (in dd/mm/yyyy format ONLY)\
            of the contact you wish to search: "))
        for i in range(len(pb)):
            if query == pb[i][3]:
                check = i
                temp.append(pb[i])

    elif choice == 5:
    # This will execute for searches based on contact category
        query = str(
            input("Please enter the category of the contact you wish to search: "))
        for i in range(len(pb)):
            if query == pb[i][4]:
                check = i
                temp.append(pb[i])
        # All contacts under query category will be shown using this feature

    else:
    # If the user enters any other choice then the search will be unsuccessful
        print("Invalid search criteria")
        return -1
    # returning -1 indicates that the search was unsuccessful

    # all the searches are stored in temp and all the results will be displayed with
    # the help of display function

    if check == -1:
        return -1
        # returning -1 indicates that the query did not exist in the directory
    else:
        display_all(temp)
        return check
        # we're just returning a index value wiz not -1 to calling function just to notify
        # that the search worked successfully

# this function displays all content of phonebook pb
def display_all(pb):
    if not pb:
    # if display function is called after deleting all contacts then the len will be 0
    # And then without this condition it will throw an error
        print("List is empty: []")
    else:
        for i in range(len(pb)):
            print(pb[i])

def thanks():
# A simple gesture of courtesy towards the user to enhance user experience
    print("********************************************************************")
    print("Thank you for using our Smartphone directory system.")
    print("Please visit again!")
    print("********************************************************************")
    sys.exit("Goodbye, have a nice day ahead!")

# Main function code
print("....................................................................")
print("Hello dear user, welcome to our smartphone directory system")
print("You may now proceed to explore this directory")
print("....................................................................")
# This is solely meant for decoration purpose only.
# You're free to modify your interface as per your will to make it look interactive

ch = 1
pb = initial_phonebook()
while ch in (1, 2, 3, 4, 5):
    ch = menu()
    if ch == 1:
        pb = add_contact(pb)
    elif ch == 2:
        pb = remove_existing(pb)
    elif ch == 3:
        pb = delete_all(pb)
    elif ch == 4:
        d = search_existing(pb)
        if d == -1:
            print("The contact does not exist. Please try again")
    elif ch == 5:
        display_all(pb)
    else:
        thanks()
```

**输出:**我们将逐段看到这个程序的输出。
初始显示如下:

> …………………………………………………………..
> 亲爱的用户您好，欢迎来到我们的智能手机目录系统
> 您现在可以开始浏览这个目录了
> ..
> 请输入初始联系人数:

开始时，我们将输入 2 个联系人:

> 请输入初始联系人数:2
> []
> 按以下顺序输入联系 1 详情(仅限):
> 注:*表示必填字段
> ………………………………………………………………..
> 输入姓名*:极客
> 输入号码*:99999999999
> 输入电子邮件地址:gfg@gfg.com
> 输入出生日期(dd/mm/yy): 01/01/01
> 输入类别(家人/朋友/工作/其他):工作
> 按以下顺序输入联系人 2 的详细信息(仅限):
> 注:*表示必填字段
> ……………………………………………………..
> 输入姓名*:样本
> 输入号码*: 1234567890
> 输入电子邮件地址:
> 输入出生日期(dd/mm/yy):
> 输入类别(家人/朋友/工作/其他人):
> [' Geeks '，9999999999999，' gfg@gfg.com '，' 01/01 '，' Work']，['Sample '，1234567890，添加新联系人
> 2。移除现有触点
> 3。删除所有联系人
> 4。搜索联系人
> 5。显示所有触点
> 6。退出电话簿
> 请输入您的选择:

现在添加新联系人，根据菜单我们会按 1 :

> 请输入您的选择:1
> 输入姓名:紧急情况
> 输入号码:108
> 输入电子邮件地址:
> 输入出生日期(dd/mm/yy):
> 输入类别(家人/朋友/工作/其他):
> * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *现在可以执行以下操作
> 添加新联系人
> 2。移除现有触点
> 3。删除所有联系人
> 4。搜索联系人
> 5。显示所有触点
> 6。退出电话簿
> 请输入您的选择:

按 5 :
可以看到所有的联系人

> 请输入您的选择:5
> ['Geeks '，9999999999，' gfg@gfg.com '，' 01/01/01 '，' Work']
> ['Sample '，1234567890，None，None，None]
> ['Emergency '，108，"，"，"，"]
> * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * T4 智能手机目录
> * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *添加新联系人
> 2。移除现有触点
> 3。删除所有联系人
> 4。搜索联系人
> 5。显示所有触点
> 6。退出电话簿
> 请输入您的选择:

要删除联系人，我们必须输入 2 :

> 请输入您的选择:2
> 请输入您要删除的联系人的姓名:示例
> ['示例'，1234567890，无，无，无]
> 该查询现已被删除
> * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *您现在可以对该电话簿
> 执行以下操作添加新联系人
> 2。移除现有触点
> 3。删除所有联系人
> 4。搜索联系人
> 5。显示所有触点
> 6。退出电话簿
> 请输入您的选择:

要搜索联系人，我们必须按 4 :

> 请输入您的选择:4
> 输入搜索条件
> 1。名称
> 2。编号
> 3。邮箱号
> 4。DOB
> 5。类别(家人/朋友/工作/其他)
> 请输入:2
> 请输入您希望搜索的联系人的号码:9999999999
> ['Geeks '，9999999999999，' gfg@gfg.com '，' 01/01/01 '，' Work ']
> * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
> 智能手机目录
> * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *添加新联系人
> 2。移除现有触点
> 3。删除所有联系人
> 4。搜索联系人
> 5。显示所有触点
> 6。退出电话簿
> 请输入您的选择:

我们可以通过按 3 :
删除所有联系人

> 请输入您的选择:3
> * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *智能手机目录
> * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *您现在可以在此电话簿
> 1 上执行以下操作。添加新联系人
> 2。移除现有触点
> 3。删除所有联系人
> 4。搜索联系人
> 5。显示所有触点
> 6。退出电话簿
> 请输入您的选择:

要查看所有联系人，请按 5，因为我们刚刚删除了他们，所以不会显示任何内容:

> 请输入您的选择:5
> 列表为空:[]
> * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * T2【智能手机目录】
> * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *现在您可以对本电话本
> 1 执行以下操作。添加新联系人
> 2。移除现有触点
> 3。删除所有联系人
> 4。搜索联系人
> 5。显示所有触点
> 6。退出电话簿
> 请输入您的选择:

要退出程序，请输入 6 :

> 请输入您的选择:6
> * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *感谢您使用我们的智能手机目录系统。
> 请再次光临！
> * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * T4】