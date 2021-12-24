# 使用 Python 中的 GDAL 打开 tif 文件

> 原文:[https://www . geesforgeks . org/open-TIF-file-using-gdal-in-python/](https://www.geeksforgeeks.org/opening-tif-file-using-gdal-in-python/)

要打开光栅文件，我们需要注册驱动程序。在 python 中，每当导入 **gdal** 时，都会隐式调用 **GDALAllRegister()** 。要打开的 **tiff** 文件可以在这里[下载。](https://drive.google.com/file/d/1Zjxa5iD-L8RjP1U2gKau92YTFNeIgUGd/view?usp=sharing)

**导入模块:**从 osgeo 导入 gdal 和 ogr 模块。

## 蟒 3

```py
from osgeo import gdal, ogr
```