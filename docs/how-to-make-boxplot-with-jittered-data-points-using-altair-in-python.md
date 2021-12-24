# 如何用 Python 中的牛郎星制作抖动数据点的箱线图？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 中的牛郎星制作带有抖动数据点的 box plot/](https://www.geeksforgeeks.org/how-to-make-boxplot-with-jittered-data-points-using-altair-in-python/)

在本文中，我们将确定使用阿尔泰形成带有数据点的箱线图的方法。最新版本的阿尔泰支持制作简单的方块图。然而，当前版本的阿尔泰不支持在方块图的顶部添加抖动的数据点。因为加州理工学院的贾斯汀·博伊斯，我们将使用他的数据可视化实用程序包阿尔泰-catplot，我们将使用抖动的数据点制作箱线图。

*   [**Niulangxing**](https://www.geeksforgeeks.org/introduction-to-altair-in-python/) **:** Niulangxing is a statistical visualization library in Python. It is declarative in nature and based on Vega and Vega-Lite visual syntax. It is rapidly becoming the first choice for people to find fast and effective methods to visualize data sets. If you have used imperative visualization library like matplotlib, you will be able to correctly understand Altai's ability.
*   [t0 T0】 Catplot: Catplot is a relatively new supplement of Seaborn, which simplifies the drawing involving classification variables. In the Seaborn version. 9.0 was released in July, 2018, and the old factor diagram was changed to catplot, which made it more in line with the terms of panda and seabird.
*   **Box diagram:** We can create the following box diagram. Note that the tag is a string, which specifies a block diagram (also in the future Altair), and the code is a dictionary designated as a key-value pair.

### 所需步骤

1.  导入库
2.  导入或创建数据
3.  将 altair_catplot.catplot()方法与 jitterbox 变换一起使用。
4.  修改不同属性的值以获得更好的可视化效果(可选)。

**例 1:**

## 蟒 3

```py
# importing packages
import altair
import altair_catplot
import seaborn

# load data
tip = seaborn.load_dataset('tips')

# draw a plot
altair_catplot.catplot(tip,
                       transform ='jitterbox',
                       mark ='point',
                       encoding = dict(x = altair.X('time:N', title = None),
                                     y = altair.Y('total_bill:Q', scale = altair.Scale(zero = False)),
                                     color = altair.Color('time:N', legend = None))
                      )
```