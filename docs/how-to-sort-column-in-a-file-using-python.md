# 如何使用 Python 在文件中按列排序？

> 原文:[https://www . geesforgeks . org/如何使用 python 对文件中的列进行排序/](https://www.geeksforgeeks.org/how-to-sort-column-in-a-file-using-python/)

对于排序文件，特别是 CSV 或制表符或空格分隔的文件，我们使用熊猫和排序数据。因为熊猫提供了多种功能来达到同样的效果。但是有一点我们必须意识到，熊猫是为更大的数据集而不是更小的文件而建造的。对于小文件，我们甚至可以使用 python 提供的内置函数，不需要像 Pandas 那样安装额外的库来获取所需的。

写这篇文章的主要原因是展示我们如何使用像 sort 这样的内置函数，以所需的方式对< 10K 线的较小文件进行排序，并且仍然得到我们想要的东西。在本文中，我们将了解如何使用 sort 函数根据我们的需求定制排序，而不是依赖函数提供的默认元素方式排序。

Sort 是 python 中的一个内置列表函数，可以对任意给定的对象(如整数、浮点数、字符串)进行升序或降序排序。除此之外，它还提供了一个称为“键”的特殊属性，我们可以使用它来定制排序。对于“键”属性，我们可以传递一个像 Lambda 这样的单行函数，也可以传递一个用户定义的函数。

**语法:**

```py
sort(self, /, *, key=None, reverse=False)
```

让我们通过应用我们通常看到的两种常见数据类型，即数值数据和分类数据，来了解如何使用列表数据类型的排序函数。

**方法 1#:** 如何使用排序函数对数值数据进行排序？

从 [github 链接](https://raw.githubusercontent.com/bvvkrishna/SampleFiles/main/MallSalesData.csv)下载 MallSalesData.csv 文件到您当前的目录中，并将其保存为 MallSalesData.csv，然后下载的示例文件 MallSalesData.csv 包含关于沃尔玛商店中销售数据的信息，其中包含产品代码、生产描述和产品价格等字段。在下面的代码中，我们将使用排序函数按价格升序对下载的 CSV 文件进行排序。

## 蟒 3

```py
def my_sort(line):
    line_fields = line.strip().split(',')
    amount = float(line_fields[2])
    return amount

# opening file MallSalesData.csv
# and getting contents into a list
fp = open('MallSalesData.csv')
contents = fp.readlines()

# sorting using our custom logic
contents.sort(key=my_sort)

# printing the sorting contents to stdout
for line in contents:
    print(line)

fp.close()
```

**输出:**

```py
22633,HAND WARMER UNION JACK,11.1

22632,HAND WARMER RED POLKA DOT,11.1

85123A,WHITE HANGING HEART T-LIGHT HOLDER,15.3

22752,SET 7 BABUSHKA NESTING BOXES,15.3

71053,WHITE METAL LANTERN,20.34

84029G,KNITTED UNION FLAG HOT WATER BOTTLE,20.34

84029E,RED WOOLLY HOTTIE WHITE HEART,20.34

84406B,CREAM CUPID HEARTS COAT HANGER,22

21730,GLASS STAR FROSTED T-LIGHT HOLDER,25.5

84879,ASSORTED COLOUR BIRD ORNAMENT,54.08

```

在上面，您可以看到我们正在定义自己的自定义逻辑，即 my_sort 函数，该函数指导 sort 函数对特定字段(如价格)进行排序，以对记录进行排序。您可以在上面的输出中看到，整个文件是根据价格字段排序的。

### **这是如何工作的？**

*   当我们在 sort()函数中使用键属性时，每次列表中的一个元素(在本例中是客户购买记录)被传递给我们的函数 my_sort()。
*   my_sort 函数将按逗号分割记录，获取价格，并存储在金额变量中。
*   金额变量进一步作为 my_sort()函数的返回值返回，sort()使用该函数对记录进行排序。
*   这意味着每次 sort()函数看到数字形式的 amount()值时都会对记录进行排序。

**方法 2#:** 如何使用排序函数对分类数据进行排序？

1.从 [github 链接](https://github.com/bvvkrishna/SampleFiles/blob/main/Flights.txt)下载 Flights.txt 文件到您当前的目录中，并将文件名保存为 Flights.txt。下载的样本文件 Flights.txt 包含航班乘客的信息，例如他们的机票号码、乘客姓名、机票代码和他们正在乘坐的客舱等级。在下面的代码中，我们将使用排序功能根据他们的客舱等级对下载的文本文件进行排序。这就是经济其次是高级经济其次是商务其次是头等舱。

## 蟒 3

```py
def my_sort(line):
    flight_class = {'ECONOMY': 1,
                    'PREMIUMECONOMY': 2,
                    'BUSINESS': 3,
                    'FIRSTCLASS': 4}
    line_fields = line.strip().split()
    cabin_class = line_fields[-1]
    return flight_class[cabin_class]

# reading flights.csv and storing in list
# variable contents
fp = open('Flights.txt')
contents = fp.readlines()

# sorting based on categorical variable cabin class
contents.sort(key=my_sort)

# displaying contents on stdout after sorting
for line in contents:
    print(line)

fp.close()
```

**输出:**

```py
001 AALAM SAMIMI/MOJGAN MRS 5SZKUU ECONOMY

007 AFSHAR GHAHREMANKHANI/ARA ZYA4NT ECONOMY

010 AHMADI SOBHANI/JALEH MS 2ASCHO ECONOMY
002 ABDOLI/AHMAD DR MR 5AMBNC PREMIUMECONOMY

008 AFSHARGHAHREMANKHANI/ALI 8CP4YE PREMIUMECONOMY

003 ABDOLLAHIMOTLAGHSOMEHSA/M 6VXREM BUSINESS

009 AFSHARGHAHREMANKHANI/ARIA 8CQFCB BUSINESS

004 AFRASIABI/HASSAN MR 2Y24ER FIRSTCLASS

005 AFSHAR BAKESHLOO/LIDA MRS 8CQFCB FIRSTCLASS

006 AFSHAR GHAHREMANKHANI/ALI 25KO4X FIRSTCLASS

```

在上图中，您可以看到我们已经定义了自定义逻辑，即 my_sort 函数，该函数指导 sort 函数对名为 cabin class 的分类变量进行排序。在上面的输出中，您可以看到整个文件是按最后一个字段排序的，即客舱等级，您可以观察到记录的顺序是:经济舱，高级经济舱，商务舱，头等舱。

### **这是如何工作的？**

*   当我们在 sort()函数中使用键属性时，每当列表中的一个元素(乘客在飞机上旅行的信息)被传递给我们的函数 my_sort()时。
*   my_sort 函数将按空间分割记录，并将最后一个字段(即 cabin class)提取到变量 cabin _ class 中。
*   我们还定义了一个字典航班等级，其中我们根据我们的要求定义了客舱等级顺序，即经济舱为 1，高级经济舱为 2，依此类推。这将帮助我们发送我们想要对这些分类值进行排序的顺序。
*   一旦我们从每条记录中获得了 cabin_class，我们将在字典中检查 flight_class 提到的顺序优先级是什么，并将该值作为返回值传递给 sort()函数。
*   这意味着每次 sort()函数都会看到为飞行舱等级定义的订单优先级，并相应地对记录进行排序。

这样，我们只需使用 python 提供的基本功能，就可以定制任何类型的排序功能。同样，我们可以定制 python 的 max、min 和其他内置函数，根据我们的需求执行操作。