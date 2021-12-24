# Python |电影推荐系统的实现

> 原文:[https://www . geesforgeks . org/python-电影的实现-推荐系统/](https://www.geeksforgeeks.org/python-implementation-of-movie-recommender-system/)

推荐系统是一个根据用户的选择来预测或过滤偏好的系统。推荐系统被用于各种领域，包括电影、音乐、新闻、书籍、研究文章、搜索查询、社交标签和一般产品。
推荐系统以两种方式中的任何一种产生推荐列表–

*   **协同过滤:**协同过滤方法根据用户过去的行为(即用户购买或搜索的项目)以及其他用户做出的类似决策来构建模型。该模型然后被用于预测用户可能感兴趣的项目(或项目的评级)。
*   **基于内容的过滤:**基于内容的过滤方法使用项目的一系列离散特征，以便推荐具有相似属性的附加项目。基于内容的过滤方法完全基于对项目的描述和用户偏好的描述。它根据用户过去的偏好推荐项目。

让我们使用 Python 和 Pandas 开发一个基本的推荐系统。
让我们专注于通过建议与特定项目最相似的项目来提供基本的推荐系统，在本例中是电影。它只是告诉用户哪些电影/项目与用户的电影选择最相似。
要下载文件，请点击链接–[。tsv 文件](https://media.geeksforgeeks.org/wp-content/uploads/file.tsv)，[电影 _Id_Titles.csv](https://media.geeksforgeeks.org/wp-content/uploads/Movie_Id_Titles.csv) 。
导入带分隔符“\t”的数据集，因为文件是 tsv 文件(制表符分隔的文件)。

## 蟒蛇 3

```py
# import pandas library
import pandas as pd

# Get the data
column_names = ['user_id', 'item_id', 'rating', 'timestamp']

path = 'https://media.geeksforgeeks.org/wp-content/uploads/file.tsv'

df = pd.read_csv(path, sep='\t', names=column_names)

# Check the head of the data
df.head()
```