# 通过确定潜在的造林用地来控制污染——蟒蛇项目

> 原文:[https://www . geesforgeks . org/污染控制-通过识别-潜力-土地造林-python-project/](https://www.geeksforgeeks.org/pollution-control-by-identifying-potential-land-for-afforestation-python-project/)

该计划旨在通过建议树木的数量和种植面积来控制特定地区的污染。该计划的核心是计算机视觉。下面给出了一个示例图像，以了解我们将在本文中做什么。注意，我们将使用 **Python** 语言来实现这个项目。

### 使用的工具和技术

在这个项目中，我们使用 **numpy 和数学**来计算我们周围的区域， **PIL(Python 图像库)**进行操作。在跳到项目之前，让我们先了解这些术语。

*   [**NumPy**](https://www.geeksforgeeks.org/numpy-in-python-set-1-introduction/) **(数值 Python):** NumPy 是 Python 编程语言的一个库，增加了对大型、多维数组和矩阵的支持，以及对这些数组进行操作的大量高级数学函数的集合。
*   [**数学**](https://www.geeksforgeeks.org/python-math-module/)**:***Python 数学模块*为您提供了在应用程序中执行常见且有用的*数学计算*的能力。以下是数学模块的一些实际用途:使用阶乘计算组合和排列。用三角函数计算杆的高度。
*   [**PIL(Python 图像库):**](https://www.geeksforgeeks.org/python-pillow-a-fork-of-pil/) *Python 图像库*是 Python 编程语言的免费开源附加库，增加了对打开、操作和保存许多不同图像文件格式的支持。
*   [**OpenCV**](https://www.geeksforgeeks.org/opencv-overview/)【T4:*OpenCV*是一个跨平台的库，利用它我们可以开发实时的计算机视觉应用。它主要侧重于图像处理、视频捕获和分析，包括人脸检测和目标检测等功能。

## **分步实施**

**第一步:创建新项目**

在 PyCharm IDE 或 V.S. Code 中创建新项目

**第二步:在进入编码部分之前，你首先要做一些前置任务**

在这个项目中，我们需要一个谷歌地图提供的应用编程接口密钥。

**第三步:我们来编码地图分割**

第一步生成的卫星图像经过图像分割，通过聚焦边缘和边界来分离图像中的所有对象。图像分为建筑物、树木、水体、道路、荒地等物体。我们选择的第一个算法是均值漂移分割算法。

## 蟒蛇 3

```py
import numpy as np
import cv2
from PIL import Image
import urllib.parse
import urllib.request
import io
from math import log, exp, tan, atan, pi, ceil
from place_lookup import find_coordinates
from calc_area import afforestation_area

EARTH_RADIUS = 6378137
EQUATOR_CIRCUMFERENCE = 2 * pi * EARTH_RADIUS
INITIAL_RESOLUTION = EQUATOR_CIRCUMFERENCE / 256.0
ORIGIN_SHIFT = EQUATOR_CIRCUMFERENCE / 2.0

def latlontopixels(lat, lon, zoom):
    mx = (lon * ORIGIN_SHIFT) / 180.0
    my = log(tan((90 + lat) * pi / 360.0)) / (pi / 180.0)
    my = (my * ORIGIN_SHIFT) / 180.0
    res = INITIAL_RESOLUTION / (2 ** zoom)
    px = (mx + ORIGIN_SHIFT) / res
    py = (my + ORIGIN_SHIFT) / res
    return px, py

def pixelstolatlon(px, py, zoom):
    res = INITIAL_RESOLUTION / (2 ** zoom)
    mx = px * res - ORIGIN_SHIFT
    my = py * res - ORIGIN_SHIFT
    lat = (my / ORIGIN_SHIFT) * 180.0
    lat = 180 / pi * (2 * atan(exp(lat * pi / 180.0)) - pi / 2.0)
    lon = (mx / ORIGIN_SHIFT) * 180.0
    return lat, lon

query = input('What kinda places you want me look up? ')
results = find_coordinates(query)

zoom = 18

ullat, ullon = results['upper_left']
lrlat, lrlon = results['lower_right']

scale = 1
maxsize = 640

ulx, uly = latlontopixels(ullat, ullon, zoom)
lrx, lry = latlontopixels(lrlat, lrlon, zoom)

dx, dy = lrx - ulx, uly - lry

cols, rows = int(ceil(dx / maxsize)), int(ceil(dy / maxsize))

bottom = 120
largura = int(ceil(dx / cols))
altura = int(ceil(dy / rows))
alturaplus = altura + bottom

final = Image.new("RGB", (int(dx), int(dy)))
for x in range(cols):

    for y in range(rows):
        dxn = largura * (0.5 + x)
        dyn = altura * (0.5 + y)
        latn, lonn = pixelstolatlon(ulx + dxn, uly - dyn - bottom / 2, zoom)
        position = ','.join((str(latn), str(lonn)))
        print(x, y, position)
        urlparams = urllib.parse.urlencode({'center': position,
                                            'zoom': str(zoom),
                                            'size': '%dx%d' % (largura, alturaplus),
                                            'maptype': 'satellite',
                                            'sensor': 'false',
                                            'scale': scale,
                                            'key': 'AIzaSyA_d4uV3HqPPWbCb77VhXNYn5UcXRLAiVc'})
        urlparamsmaps = urllib.parse.urlencode({'center': position,
                                                'zoom': str(zoom),
                                                'size': '%dx%d' % (largura, alturaplus),
                                                'maptype': 'roadmap',
                                                'sensor': 'false',
                                                'scale': scale,
                                                'key': 'AIzaSyA_d4uV3HqPPWbCb77VhXNYn5UcXRLAiVc'})
        url = 'http://maps.google.com/maps/api/staticmap?' + urlparams
        url1 = 'http://maps.google.com/maps/api/staticmap?' + urlparamsmaps
        f = urllib.request.urlopen(url)
        h = urllib.request.urlopen(url1)
        image = io.BytesIO(f.read())
        imagemaps = io.BytesIO(h.read())
        im = Image.open(image)
        immaps = Image.open(imagemaps)
        im.save("map.png")
        immaps.save("map_normal.png")

        img = cv2.imread('map.png')
        img_maps = cv2.imread('map_normal.png')
        shifted = cv2.pyrMeanShiftFiltering(img, 7, 30)
        shifted_normal = cv2.pyrMeanShiftFiltering(img_maps, 7, 30)
        gray = cv2.cvtColor(shifted, cv2.COLOR_BGR2GRAY)
        ret, thresh = cv2.threshold(
            gray, 0, 255, cv2.THRESH_BINARY | cv2.THRESH_OTSU)
        hsv = cv2.cvtColor(shifted, cv2.COLOR_BGR2HSV)
        hsv_normal = cv2.cvtColor(shifted_normal, cv2.COLOR_BGR2HSV)

        lower_trees = np.array([10, 0, 30])
        higher_trees = np.array([180, 100, 95])

        lower_houses = np.array([90, 10, 100])
        higher_houses = np.array([255, 255, 255])

        lower_roads = np.array([0, 0, 250])
        higher_roads = np.array([20, 20, 255])

        lower_feilds = np.array([0, 50, 100])
        higher_feilds = np.array([50, 255, 130])

        lower_feilds_blue = np.array([0, 80, 100])
        higher_feilds_blue = np.array([255, 250, 255])

        masktree = cv2.inRange(hsv, lower_trees, higher_trees)
        maskhouses = cv2.inRange(hsv, lower_houses, higher_houses)
        maskroads = cv2.inRange(hsv_normal, lower_roads, higher_roads)
        maskfeilds = cv2.inRange(hsv, lower_feilds, higher_feilds)
        gausssion_blur_maskfields = cv2.GaussianBlur(maskfeilds, (15, 15), 0)
        gausssion_blur_masktree = cv2.GaussianBlur(masktree, (15, 15), 0)
        blue_limiter = cv2.inRange(hsv, lower_feilds_blue, higher_feilds_blue)
        res_roads = cv2.bitwise_and(img_maps, img, mask=maskroads)
        # res_houses = cv2.bitwise_and(img,img,mask=maskhouses)
        res_feilds = cv2.bitwise_and(img, img, mask=gausssion_blur_maskfields)
        res_trees = cv2.bitwise_and(img, img, mask=masktree)

        # show the output image
        cv2.imshow('res', res_trees)
        cv2.imshow('res_fields', res_feilds)
        cv2.imshow('res_roads', res_roads)

        # cv2.imshow('res_houses',res_houses)
        # cv2.imshow('mask',maskfeilds)
        cv2.imshow('img', img)

        # cv2.imshow("hsv", hsv)
        cv2.waitKey(0)
        cv2.destroyAllWindows()

tot_land_area_acres, number_of_trees = afforestation_area()
```

**第四步:我们来编码地点查找**

要求用户输入程序必须在其上执行的区域的名称。该区域的卫星图像将被刮擦和缩放，从而生成地图的清晰图像，在该图像上可以进行图像分割。

## 蟒蛇 3

```py
import urllib.parse
import requests

def find_coordinates(query):

    main_api = 'https://maps.googleapis.com/maps/api/place/textsearch/json?'
    url = main_api + \
        urllib.parse.urlencode({'query': query}) + '&key=Your API Key'

    json_data = requests.get(url).json()
    json_status = json_data['status']
    print('\nAPI Status :' + json_status)

    if json_status == 'OK':

        location_details = {
            'name_of_place': json_data['results'][0]['name'],
            'formatted_address': json_data['results'][0]['formatted_address'],
            'location': json_data['results'][0]['geometry']['location'],
            'upper_left': (json_data['results'][0]['geometry']['viewport']['northeast']['lat'],
                           json_data['results'][0]['geometry']['viewport']['southwest']['lng']),
            'lower_right': (json_data['results'][0]['geometry']['viewport']['southwest']['lat'], 
                            json_data['results'][0]['geometry']['viewport']['northeast']['lng']),
        }

        return location_details
```

**第五步:我们来编码计算面积**

我们将找到给定地区的污染水平。根据这个级别，我们将找到使该特定级别恢复正常所需的树的数量。在这个过程中，我们需要训练一个分类器，它可以识别建筑物、树木，最重要的是，自由的土地。上述方法使用的泽尼克矩将用作这些片段的特征。分类器是用“建筑物”、“树木”、“水”、“自由土地”和“道路”等标签训练的。培训结束后，我们只需要找到“自由之地”标签下的部分。

## 蟒蛇 3

```py
import cv2
import numpy as np

def afforestation_area():

    img = cv2.imread('map.png')
    shifted = cv2.pyrMeanShiftFiltering(img, 7, 30)
    gray = cv2.cvtColor(shifted, cv2.COLOR_BGR2GRAY)
    ret, thresh = cv2.threshold(
        gray, 0, 255, cv2.THRESH_BINARY | cv2.THRESH_OTSU)
    hsv = cv2.cvtColor(shifted, cv2.COLOR_BGR2HSV)

    lower_trees = np.array([10, 0, 10])
    higher_trees = np.array([180, 180, 75])

    lower_houses = np.array([90, 10, 100])
    higher_houses = np.array([255, 255, 255])

    lower_roads = np.array([90, 10, 100])
    higher_roads = np.array([100, 100, 100])

    lower_feilds = np.array([0, 20, 100])
    higher_feilds = np.array([50, 255, 255])

    lower_feilds_blue = np.array([0, 80, 100])
    higher_feilds_blue = np.array([255, 250, 255])

    masktree = cv2.inRange(hsv, lower_trees, higher_trees)
    maskhouses = cv2.inRange(hsv, lower_houses, higher_houses)
    maskroads = cv2.inRange(hsv, lower_roads, higher_roads)
    maskfeilds_houses = cv2.inRange(hsv, lower_feilds, higher_feilds)
    blue_limiter = cv2.inRange(hsv, lower_feilds_blue, higher_feilds_blue)
    maskfeilds = maskfeilds_houses
    res = cv2.bitwise_and(img, img, mask=maskfeilds)

    print(res.shape)  # (640, 622, 3)
    print(np.count_nonzero(res))  # 679089

    print("number of pixels", res.size//3)
    tot_pixels = res.size//3
    # print("number of pixels: row x col", res.)

    no_of_non_zero_pixels_rgb = np.count_nonzero(res)
    row, col, channels = res.shape  # 152886
    print("percentage of free land : ", (no_of_non_zero_pixels_rgb /
                                         (row*col*channels)))  # 0.5686369573954984
    percentage_of_land = no_of_non_zero_pixels_rgb/(row*col*channels)

    # https://www.unitconverters.net/typography/centimeter-to-pixel-x.htm
    # says 1 cm = 37.795275591 pixels
    cm_2_pixel = 37.795275591
    print("row in cm ", row/cm_2_pixel)
    print("col in cm ", col/cm_2_pixel)

    row_cm = row/cm_2_pixel
    col_cm = col/cm_2_pixel
    tot_area_cm = tot_pixels/(row_cm*col_cm)
    tot_area_cm_land = tot_area_cm*percentage_of_land

    print("Total area in cm^2 : ", tot_area_cm_land)

    # in google maps 2.2cm = 50m => 1cm = 22.727272727272727m
    # in real life at zoom 18 1cm^2 = (22.727272727272727m)^2
    # = 516.5289256198347 m^2
    print("Total area in m^2 : ", tot_area_cm_land*(516.5289256198347))
    tot_area_m_actual_land = tot_area_cm_land*(516.5289256198347)

    # 1 m^2 = 0.000247105 acres :: source Google
    tot_area_acre_land = tot_area_m_actual_land*0.000247105
    print("Total area in acres : ", tot_area_acre_land)

    # https://www.treeplantation.com/tree-spacing-calculator.html
    # says if you have 2 ft between rows, and 2ft between 
    # trees will can take 10890 trees per acre.
    number_of_trees = tot_area_acre_land*10890
    print(f"{round(number_of_trees)} number of trees can be planted in\
    {tot_area_acre_land} acres.")

    return tot_area_acre_land, round(number_of_trees)

    # show the output image
    # cv2.imshow('res',res)

    # cv2.imshow('mask',maskfeilds)
    # cv2.imshow('img', img)

    #cv2.imshow("hsv", hsv)
    # cv2.waitKey(delay=0)
    # cv2.destroyAllWindows()

# afforestation_area()
```

**第六步:我们给主文件**编码

## 蟒蛇 3

```py
import numpy as np
import cv2
from PIL import Image
import urllib.parse
import urllib.request
import io
from math import log, exp, tan, atan, pi, ceil
from place_lookup import find_coordinates

EARTH_RADIUS = 6378137
EQUATOR_CIRCUMFERENCE = 2 * pi * EARTH_RADIUS
INITIAL_RESOLUTION = EQUATOR_CIRCUMFERENCE / 256.0
ORIGIN_SHIFT = EQUATOR_CIRCUMFERENCE / 2.0

def latlontopixels(lat, lon, zoom):
    mx = (lon * ORIGIN_SHIFT) / 180.0
    my = log(tan((90 + lat) * pi / 360.0)) / (pi / 180.0)
    my = (my * ORIGIN_SHIFT) / 180.0
    res = INITIAL_RESOLUTION / (2 ** zoom)
    px = (mx + ORIGIN_SHIFT) / res
    py = (my + ORIGIN_SHIFT) / res
    return px, py

def pixelstolatlon(px, py, zoom):
    res = INITIAL_RESOLUTION / (2 ** zoom)
    mx = px * res - ORIGIN_SHIFT
    my = py * res - ORIGIN_SHIFT
    lat = (my / ORIGIN_SHIFT) * 180.0
    lat = 180 / pi * (2 * atan(exp(lat * pi / 180.0)) - pi / 2.0)
    lon = (mx / ORIGIN_SHIFT) * 180.0
    return lat, lon

def calculate_area(res):
    """
    Args:
        Takes the transformed image as input
    Returns:
        :tot_area_acre_land: empty area in acres.
        :trees: rounded number of trees in the possible area.
    """
    # print(res.shape) # (640, 622, 3)
    # print(np.count_nonzero(res)) # 679089

    # print("number of pixels", res.size//3)
    tot_pixels = res.size//3
    # print("number of pixels: row x col", res.)

    no_of_non_zero_pixels_rgb = np.count_nonzero(res)
    row, col, channels = res.shape  # 152886

    percentage_of_land = no_of_non_zero_pixels_rgb/(row*col*channels)

    # https://www.unitconverters.net/typography/centimeter-to-pixel-x.htm
    # says 1 cm = 37.795275591 pixels
    cm_2_pixel = 37.795275591
    # print("row in cm ", row/cm_2_pixel)
    # print("col in cm ", col/cm_2_pixel)

    row_cm = row/cm_2_pixel
    col_cm = col/cm_2_pixel
    tot_area_cm = tot_pixels/(row_cm*col_cm)
    tot_area_cm_land = tot_area_cm*percentage_of_land

    # print("Total area in cm^2 : ", tot_area_cm_land)

    # in google maps 2.2cm = 50m => 1cm = 22.727272727272727 m 
    # in real life at zoom 18 1cm^2 = (22.727272727272727m)^2 
    # = 516.5289256198347 m^2
    tot_area_m_actual_land = tot_area_cm_land*(516.5289256198347)

    # 1 m^2 = 0.000247105 acres :: source Google
    tot_area_acre_land = tot_area_m_actual_land*0.000247105
    # print("Total area in acres : ", tot_area_acre_land)

    # https://www.treeplantation.com/tree-spacing-calculator.html
    # says if you have 2 ft between rows, and 2ft between trees 
    # will can take 10890 trees per acre.

    number_of_trees = tot_area_acre_land*10890
    # print(f"{round(number_of_trees)} number of trees can be planted
    # in {tot_area_acre_land} acres.")

    return tot_area_acre_land, round(number_of_trees)

def air_pollution_core(ullat, ullon, lrlat, lrlon, results):

    zoom = 18
    scale = 1
    maxsize = 640

    ulx, uly = latlontopixels(ullat, ullon, zoom)
    lrx, lry = latlontopixels(lrlat, lrlon, zoom)

    dx, dy = lrx - ulx, uly - lry

    cols, rows = int(ceil(dx / maxsize)), int(ceil(dy / maxsize))

    bottom = 120
    largura = int(ceil(dx / cols))
    altura = int(ceil(dy / rows))
    alturaplus = altura + bottom

    final = Image.new("RGB", (int(dx), int(dy)))
    total_acres_place, total_trees = 0., 0.
    total_tile_results = dict()
    for x in range(cols):
        for y in range(rows):
            dxn = largura * (0.5 + x)
            dyn = altura * (0.5 + y)
            latn, lonn = pixelstolatlon(
                ulx + dxn, uly - dyn - bottom / 2, zoom)
            position = ','.join((str(latn), str(lonn)))
            # print(x, y, position)
            urlparams = urllib.parse.urlencode({'center': position,
                                                'zoom': str(zoom),
                                                'size': '%dx%d' % (largura, alturaplus),
                                                'maptype': 'satellite',
                                                'sensor': 'false',
                                                'scale': scale,
                                                'key': 'YOUR_API_HERE'})
            url = 'http://maps.google.com/maps/api/staticmap?' + urlparams
            f = urllib.request.urlopen(url)
            image = io.BytesIO(f.read())
            im = Image.open(image)
            im.save("map_{}_{}_{}.png".format(x, y, position))

            img = cv2.imread("map_{}_{}_{}.png".format(x, y, position))
            shifted = cv2.pyrMeanShiftFiltering(img, 7, 30)
            gray = cv2.cvtColor(shifted, cv2.COLOR_BGR2GRAY)
            ret, thresh = cv2.threshold(
                gray, 0, 255, cv2.THRESH_BINARY | cv2.THRESH_OTSU)
            hsv = cv2.cvtColor(shifted, cv2.COLOR_BGR2HSV)

            lower_trees = np.array([10, 0, 10])
            higher_trees = np.array([180, 180, 75])

            lower_houses = np.array([90, 10, 100])
            higher_houses = np.array([255, 255, 255])

            lower_roads = np.array([90, 10, 100])
            higher_roads = np.array([100, 100, 100])

            lower_feilds = np.array([0, 20, 100])
            higher_feilds = np.array([50, 255, 255])

            lower_feilds_blue = np.array([0, 80, 100])
            higher_feilds_blue = np.array([255, 250, 255])

            masktree = cv2.inRange(hsv, lower_trees, higher_trees)
            maskhouses = cv2.inRange(hsv, lower_houses, higher_houses)
            maskroads = cv2.inRange(hsv, lower_roads, higher_roads)
            maskfeilds_houses = cv2.inRange(hsv, lower_feilds, higher_feilds)
            blue_limiter = cv2.inRange(
                hsv, lower_feilds_blue, higher_feilds_blue)
            maskfeilds = maskfeilds_houses
            res = cv2.bitwise_and(img, img, mask=maskfeilds)

            area_in_acres, number_of_trees = calculate_area(res)
            total_acres_place += area_in_acres
            total_trees += number_of_trees
            # print(f"area: {area_in_acres}, no of trees: {number_of_trees}")

            tile_results = {
                "name_of_tile_image": "map_{}_{}_{}.png".format(x, y, position),
                "area_acres": area_in_acres,
                "number_of_trees": number_of_trees
            }
            # print(tile_results)
            total_tile_results["{}_{}_{}".format(
                x, y, position)] = tile_results

            # uncomment below for viewing the output images
            # cv2.imshow('res',res)
            # cv2.imshow('img', img)
            # cv2.waitKey(delay=2000)
            # cv2.destroyAllWindows()

    # print(total_tile_results)
    results["total_tile_results"] = total_tile_results
    results["total_acres_of_land"] = total_acres_place
    results["total_number_of_trees"] = total_trees
    return results

def location_based_estimation(place):
    """
    :place: is a string that expects a name of a place
    """
    results = find_coordinates(place)

    ullat, ullon = results['upper_left']
    lrlat, lrlon = results['lower_right']

    returning_json = air_pollution_core(ullat, ullon, lrlat, lrlon, results)
    return returning_json

def coordinates_based_estimation(ullat, ullon, lrlat, lrlon):
    """
    :upperleft: a string expecting upperleft coordinates of 
    the tile you are expecting. ex : '12.92,79.11'
    :lowerright: a string expecting lowerright coordinates of
    the tile you are expecting. ex :'12.91,79.13'
    """
    # print(f"{upperleft.replace('\"','')}")
    # ullat, ullon = map(float, upperleft.split(','))
    # lrlat, lrlon = map(float, lowerright.split(','))
    results = dict()

    returning_json = air_pollution_core(ullat, ullon, lrlat, lrlon, results)
    return returning_json
```

**输出:**

![](img/62913695e3c74b29c4dd93fa2ffdf374.png)

**完整的项目结构就是这样的。**

![](img/386dd0bbdd878a9d231e9ab2e00433d5.png)

**github link:**[https://github . com/abhi ishiki 2912/air contamination-analysis](https://github.com/abhishektyagi2912/airpollution-analyses)