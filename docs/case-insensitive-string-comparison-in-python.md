# Python 中不区分大小写的字符串比较

> 原文:[https://www . geesforgeks . org/不区分大小写-python 字符串比较/](https://www.geeksforgeeks.org/case-insensitive-string-comparison-in-python/)

我们通常使用 Python 列表来存储项目。在线购物应用程序可能包含一个项目列表，以便用户可以从项目列表中搜索该项目。例如，我们的购物应用程序有一个它销售的笔记本电脑列表。榜单包含很多品牌，其中一个就是‘联想’。如果我们想买一台联想品牌的笔记本电脑，我们会去购物应用的搜索栏搜索“联想”。然后显示联想笔记本电脑的所有型号。但有时用户可能会用小写字母输入“lenovo”，或者用大写字母输入“LENOVO”。即便如此，它也应该显示联想笔记本电脑的所有型号。这意味着我们应该执行不区分大小写的检查。

不区分大小写意味着您正在比较的字符串应该与要比较的字符串完全相同，但两个字符串都可以是大写或小写。(即。，不同情况下)

**例 1:转换为小写进行比较**

在本例中，用户字符串和每个列表项都被转换为小写，然后进行比较。

T3】蟒 3T5

```
# conversion to lowercase for search

#function to search item
def check_Laptops():

    laptops = ['Msi', 'Lenovo', 'Hp', 'Dell']

    your_laptop = 'lenovo'

    # 'lenovo' is in lower case but it is present in the list of laptops.

    for lapy in laptops:

      #convert to lowercase and compare
        if your_laptop.lower() == lapy.lower():

            return True

    else:

        return False

# If the function returns true 
if check_Laptops():

    print('Laptop is present')

# If function returns false
else:

    print('Laptop is not present')
```

T6T8**输出**T1

**例 2:转换为大写进行比较**

在本例中，用户字符串和每个列表项都被转换为大写，然后进行比较。

T3】蟒 3T5

```
# concersion to upper case

# Function to search item
def check_Laptops():

  laptops = ['Msi', 'Lenovo', 'Hp', 'Dell']

  your_laptop = 'HP'

  # 'HP' is in upper case but it is
  # present in the list of laptops.

  for lapy in laptops:

    # convert to uppercase and compare
      if your_laptop.upper() == lapy.upper():

          return True

  else:

      return False

if check_Laptops():

  #If the function is true
  print('Laptop is present')

else:

  #If the function returns false
  print('Laptop is not present')
```

T6T8**输出**T1

**例 3:**

在本例中，字符串不在列表中。因此不区分大小写的搜索也会返回 **false** 。

T5】蟒 3T7

```
# Function to search item
def check_Laptops():

  laptops = ['Msi', 'Lenovo', 'Hp', 'Dell']

  your_laptop = 'Acer'

  for lapy in laptops:

    #convert to lower and compare
      if your_laptop.lower() == lapy.lower():
          return True

  else:
      return False

if check_Laptops():

  # If the function returns false
  print('Laptop is present')

else:

  # If the function returns false
  print('Laptop is not present')
```

T8T10**输出**T1

**实施例 4:使用 casefold()** 进行比较

casefold()方法的工作原理类似于 lower()方法。但是与 lower()方法相比，它通过移除字符串中存在的所有大小写差异来执行严格的字符串比较。在德语中， **β** 相当于“ **ss** ”。但是每个用户可能都不知道德语，所以 casefold()方法将德语字母“β”转换为“ss”，而我们不能使用 lower()方法将德语字母“β”转换为“ss”。

在本例中，我们正在检查教室列表中是否有我们的教室。

T3】蟒 3T5

```
#initial list
classrooms=['class1','class2','CLASS3','class4','class5']

# class to be searched
class_room='claß3'

#' claß3' means 'class3'

#function to search item
def search_classroom():
   for classes in classrooms:
       if class_room.casefold()==classes.casefold():
           return True

   else:
       return False

if search_classroom():

  # If function returns true
   print('Classroom you are searching is present')

else:

  # If function returns false
   print('Classroom you are searching is not present')
```

T6T8**输出**T1

这些是 Python 中不区分大小写的字符串比较方法。