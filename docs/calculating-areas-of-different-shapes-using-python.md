# 使用 Python 计算不同形状的面积

> 原文:[https://www . geeksforgeeks . org/使用 python 计算不同形状的面积/](https://www.geeksforgeeks.org/calculating-areas-of-different-shapes-using-python/)

我们将制作一个 Python 程序来计算一些数学形状的面积。

**示例:**

```
Input: shape name = "Rectangle"
       length = 10
       breadth = 15
Output: Area: 150

Input: shape name = "Square"
       side = 10
Output: Area: 100
```

**进场:**

在这个程序中，我们将要求用户输入形状的名称。如果它存在于我们的程序中，那么我们将继续根据它们各自的公式找到输入形状的区域。如果该形状不存在，我们将打印“对不起！我们找不到这个形状。”屏幕上的信息。

下面是实现:

## 蟒蛇 3

```
# define a function for calculating
# the area of a shapes
def calculate_area(name):\

  # converting all characters
  # into lower cases
  name = name.lower()

  # check for the conditions
  if name == "rectangle":
    l = int(input("Enter rectangle's length: "))
    b = int(input("Enter rectangle's breadth: "))

    # calculate area of rectangle
    rect_area = l * b
    print(f"The area of rectangle is
          {rect_area}.")

  elif name == "square":
    s = int(input("Enter square's side length: "))

    # calculate area of square
    sqt_area = s * s
    print(f"The area of square is
          {sqt_area}.")

  elif name == "triangle":
    h = int(input("Enter triangle's height length: "))
    b = int(input("Enter triangle's breadth length: "))

    # calculate area of triangle
    tri_area = 0.5 * b * h
    print(f"The area of triangle is
          {tri_area}.")

  elif name == "circle":
    r = int(input("Enter circle's radius length: "))
    pi = 3.14

    # calculate area of circle
    circ_area = pi * r * r
    print(f"The area of triangle is
          {circ_area}.")

  elif name == 'parallelogram':
    b = int(input("Enter parallelogram's base length: "))
    h = int(input("Enter parallelogram's height length: "))

    # calculate area of parallelogram
    para_area = b * h
    print(f"The area of parallelogram is
          {para_area}.")

  else:
    print("Sorry! This shape is not available")

# driver code
if __name__ == "__main__" :

  print("Calculate Shape Area")
  shape_name = input("Enter the name of shape whose area you want to find: ")

  # function calling
  calculate_area(shape_name)
```

**输出:**

```
Calculate Shape Area
Enter the name of shape whose area you want to find: rectangle
Enter rectangle's length: 10
Enter rectangle's breadth: 15
The area of rectangle is 150.
```