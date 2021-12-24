# 投影剖面法

> 原文:[https://www.geeksforgeeks.org/projection-profile-method/](https://www.geeksforgeeks.org/projection-profile-method/)

在图像处理中，投影轮廓指的是从二维图像沿着一个轴的命中/肯定总和的投影。投影轮廓法主要用于文本文档中文本对象的分割。

**解决方案:**

> **注**:对于阈值图像或二值化图像计算投影轮廓，其中阈值图像是像素值为 0 或 255 的灰度图像。对于像素值 0 和 255，图像像素分别由 1 和 0 代替。

针对不同的轴分别计算投影轮廓。沿垂直轴的投影剖面称为垂直投影剖面。每一列的垂直投影轮廓计算为该列内所有行像素值的总和。水平投影轮廓是图像沿水平轴的投影轮廓。每一行的水平投影轮廓计算为该行内所有列像素值的总和。

**水平投影剖面的代码实现:**

## C++

```
#include <bits/stdc++.h>
using namespace std;

// Function to generate horizontal projection profile
vector<int> getHorizontalProjectionProfile(
    vector<vector<int> > image, int rows, int cols)
{

    for (int i = 0; i < rows; i++)
    {
        for (int j = 0; j < cols; j++)
        {
            // Convert black spots to ones
            if (image[i][j] == 0)
            {
                image[i][j] = 1;
            }
            // Convert white spots to zeros
            else if (image[i][j] == 255)
            {
                image[i][j] = 0;
            }
        }
    }

    vector<int> horizontal_projection(rows, 0);

    // Calculate sum of 1's for every row
    for (int i = 0; i < rows; i++)
    {
        // Sum all 1's
        for (int j = 0; j < cols; j++)
        {
            horizontal_projection[i] += image[i][j];
        }
    }

    return horizontal_projection;
}
// Driver Function
int main()
{
    int rows = 5, cols = 3;
    vector<vector<int> > image = { { 0, 0, 0 },
        { 0, 255, 255 },
        { 0, 0, 0 },
        { 0, 255, 255 },
        { 0, 0, 0 }
    };

    vector<int> horizontal_projection = getHorizontalProjectionProfile(
                                            image, rows, cols);

for (auto it : horizontal_projection)
    {
        cout << it << " ";
    }
    return 0;
}
```

## 蟒蛇 3

```
import numpy as np

# Function to generate horizontal projection profile
def getHorizontalProjectionProfile(image):

    # Convert black spots to ones
    image[image == 0]   = 1
    # Convert white spots to zeros
    image[image == 255] = 0

    horizontal_projection = np.sum(image, axis = 1) 

    return horizontal_projection

# Driver Function
if __name__ == '__main__':

    rows = 5
    cols = 3
    image = np.array([[0, 0, 0],
            [0, 255, 255],
            [0, 0, 0],
            [0, 255, 255],
            [0, 0, 0]])

    horizontal_projection = getHorizontalProjectionProfile(image.copy())

    print(*horizontal_projection)
```

**Output:**

```
3 1 3 1 3

```

**垂直投影剖面的代码实现:**

## C++

```
#include <bits/stdc++.h>
using namespace std;

// Function to generate vertical projection profile
vector<int> getVerticalProjectionProfile(
    vector<vector<int> > image, int rows, int cols)
{

    for (int i = 0; i < rows; i++)
    {
        for (int j = 0; j < cols; j++)
        {
            // Convert black spots to ones
            if (image[i][j] == 0)
            {
                image[i][j] = 1;
            }
            // Convert white spots to zeros
            else if (image[i][j] == 255)
            {
                image[i][j] = 0;
            }
        }
    }

    vector<int> vertical_projection(cols, 0);

    // Calculate sum of 1's for every column
    for (int j = 0; j < cols; j++)
    {
        // Sum all 1's
        for (int i = 0; i < rows; i++)
        {
            vertical_projection[j] += image[i][j];
        }
    }

    return vertical_projection;
}

// Driver Function
int main()
{
    int rows = 5, cols = 3;
    vector<vector<int> > image = { { 0, 0, 0 },
        { 0, 255, 255 },
        { 0, 0, 0 },
        { 0, 255, 255 },
        { 0, 0, 0 }
    };

    vector<int> vertical_projection = getVerticalProjectionProfile(
                                          image, rows, cols);

for (auto it : vertical_projection)
    {
        cout << it << " ";
    }
    return 0;
}
```

## 蟒蛇 3

```
import numpy as np

# Function to generate vertical projection profile
def getVerticalProjectionProfile(image):

    # Convert black spots to ones 
    image[image == 0]   = 1
    # Convert white spots to zeros 
    image[image == 255] = 0

    vertical_projection = np.sum(image, axis = 0)

    return vertical_projection

# Driver Function
if __name__ == '__main__':

    rows = 5
    cols = 3
    image = np.array([[0, 0, 0],
            [0, 255, 255],
            [0, 0, 0],
            [0, 255, 255],
            [0, 0, 0]])

    vertical_projection = getVerticalProjectionProfile(image.copy())

    print(*vertical_projection)
```

**Output:**

```
5 3 3

```

**时间复杂度** : O(行*列)
T3】空间复杂度 : O(行*列)