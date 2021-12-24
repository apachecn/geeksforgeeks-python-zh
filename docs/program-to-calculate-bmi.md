# 体重指数计算程序(身体质量指数)

> 原文:[https://www.geeksforgeeks.org/program-to-calculate-bmi/](https://www.geeksforgeeks.org/program-to-calculate-bmi/)

**体重指数(身体质量指数)**或**克托莱指数**是从男性或女性个体的体重(体重)和身高得出的值。身体质量指数定义为身体质量除以身体高度的平方，通常以千克/平方米为单位表示，由千克为单位的质量和米为单位的高度得出。公式为:

```
BMI = (mass or weight)/(height*height)
where,
mass or weight is in Kg,
height is in meters
```

**例:**

```
Input : height(in meter): 1.79832
weight(in Kg): 70
Output : The BMI is 21.64532402096181, so Healthy.
Explanation : 70/(1.79832*1.79832)

Input : height(in meter): 1.58496
weight(in Kg): 85
Output : The BMI is 33.836256857260594 so Suffering from Obesity
Explanation : 70/(1.58496*1.58496)
```

## 蟒蛇 3

```
#Python program to illustrate
# how to calculate BMI
def BMI(height, weight):
    bmi = weight/(height**2)
    return bmi

# Driver code
height = 1.79832
weight = 70

# calling the BMI function
bmi = BMI(height, weight)
print("The BMI is", format(bmi), "so ", end='')

# Conditions to find out BMI category
if (bmi < 18.5):
    print("underweight")

elif ( bmi >= 18.5 and bmi < 24.9):
    print("Healthy")

elif ( bmi >= 24.9 and bmi < 30):
    print("overweight")

elif ( bmi >=30):
    print("Suffering from Obesity")
```

输出:

```
The BMI is 21.64532402096181 so Healthy
```