# Python |使用 Geopy 计算两地距离

> 原文:[https://www . geeksforgeeks . org/python-计算两地距离-使用-geopy/](https://www.geeksforgeeks.org/python-calculate-distance-between-two-places-using-geopy/)

GeoPy 是一个 Python 库，让用户更容易进行地理计算。在本文中，我们将看到如何用两种方法计算地球上两点之间的距离。

**如何安装 GeoPy？**

```
pip install geopy
```

**测地线距离:**
是**任意曲面**上两点间最短路径的长度。在我们的例子中，表面是地球。下面的程序说明了如何根据经纬度数据计算测地线距离。

```
# Importing the geodesic module from the library
from geopy.distance import geodesic

# Loading the lat-long data for Kolkata & Delhi
kolkata = (22.5726, 88.3639)
delhi = (28.7041, 77.1025)

# Print the distance calculated in km
print(geodesic(kolkata, delhi).km)
```

**输出:**

```
1318.13891581683
```

**大圆距离:**
是**球体**上两点间最短路径的长度。在这种情况下，地球被认为是一个完美的球体。下面的程序说明了如何从经纬度数据计算大圆距离。

```
# Importing the great_circle module from the library
from geopy.distance import great_circle

# Loading the lat-long data for Kolkata & Delhi
kolkata = (22.5726, 88.3639)
delhi = (28.7041, 77.1025)

# Print the distance calculated in km
print(great_circle(kolkata, delhi).km)
```

**输出:**

```
1317.7554645657162
```

参考:[https://geopy.readthedocs.io/en/stable/](https://geopy.readthedocs.io/en/stable/)