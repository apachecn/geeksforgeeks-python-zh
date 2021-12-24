# 用 matlab 绘制印度国旗

> 原文:[https://www . geesforgeks . org/draw-Indian-flag-use-MATLAB/](https://www.geeksforgeeks.org/draw-indian-flag-using-matlab/)

在数字图像处理中，彩色图像以三维矩阵表示。图像可以用各种颜色模型来表示，例如 RGB(红、绿、蓝)模型、HSV(色调、饱和度、值)模型、YQ(亮度-同相正交)模型、CMYK(青色、品红色、黄色、黑色)模型。通常，图像以 RGB 模型表示。矩阵的第一个通道是红色，第二个通道是绿色，第三个通道是蓝色。
**进场绘制印度国旗**

*   首先，我们需要创建一个 300X600X3 的矩阵，并用白色填充矩阵。300 是行数，600 是列数。对于彩色图像，需要 3 个通道，因此 3 代表 RGB(红、绿、蓝)通道。

```
img=uint8(zeros(300, 600, 3))
```

*   将矩阵分成三部分(0-100)行表示藏红花色，(101-200)行表示白色和 ashok chakra，(201-300)行表示绿色。
*   从第 1 行到第 100 行，用藏红花色(255，153，51)填充矩阵。

```
img(1:100, 1:600, 1)=255;
img(1:100, 1:600, 2)=153;
img(1:100;1:600, 3)=51;
```

*   从第 201 行到第 300 行，用绿色(19，136，8)填充矩阵。

```
img(201:300, 1:600, 1)=19;
img(201:300, 1:600, 2)=136;
img(201:300, 1:600, 3)=8;
```

*   为了制造一个脉轮，首先我们需要理解两个给定坐标之间的距离方程。

```
(distance)2=(x2-x1)2+(y2-y1)2
```

*   (x1，y1)和(x2，y2)是两个给定的坐标。
*   利用上面的等式，我们可以做一个阿肖克脉轮的圆。矩阵和圆的中心坐标是(150，300)。画圆的内径是 40，外径是 45。
*   阿肖克脉轮相邻两根辐条之间的角度为(360/n)=15 <sup>o</sup> ，其中 n(辐条数)=24。atand 是一个用来求角度的 MATLAB 函数。

实现如下:

## 矩阵实验室

```
% MATLAB code to draw Indian flag

% initialising a zero matrix of 300X600X3
flag=uint8(zeros(300, 600, 3));
flag(:, :, :)=255;
%Saffron Color
flag(1:100, :, 1)=255;
flag(1:100, :, 2)=153;
flag(1:100, :, 3)=51;

%Green Color
flag(200:300, :, 1)=19;
flag(200:300, :, 2)=136;
flag(200:300, :, 3)=8;

%Ashok Chakra
for i=1:300
    for j=1:600
        if sqrt(power(i-150, 2)+ power(j-300, 2))>=40
            if sqrt(power(i-150, 2)+ power(j-300, 2))<=45
                flag(i, j, 1:2)=0;
            end
        end
    end
end
for i=110:190
    for j=260:340
        dist= (sqrt(power(i-150, 2)+power(j-300, 2)));
        k=round(atand((300-j)/(150-i)));
        if dist<=40 && mod(k, 15)==0
            flag(i, j, 1:2)=0;
        end
    end
end
% displaying the matrix as image
figure, imshow(flag);
```