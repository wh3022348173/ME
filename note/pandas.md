## 介绍

Pandas 的主要数据结构是 Series （一维数据）与 DataFrame（二维数据）。

### 功能

- 数据清洗：处理缺失数据、重复数据等。
- 数据转换：改变数据的形状、结构或格式。
- 数据分析：进行统计分析、聚合、分组等。
- 数据可视化：通过整合 Matplotlib 和 Seaborn 等库，可以进行数据可视化。

## Serious

 类似于一维数组或列表，是由一组数据以及与之相关的数据标签（索引）构成。Series 可以看作是 DataFrame 中的一列，也可以是单独存在的一维数据结构。

- **索引：** 每个 `Series` 都有一个索引，它可以是整数、字符串、日期等类型。如果没有显式指定索引，Pandas 会自动创建一个默认的整数索引。
- **数据类型：** `Series` 可以容纳不同数据类型的元素，包括整数、浮点数、字符串等

```python
pandas.Series( data, index, dtype, name, copy)
```

- **data**：一组数据(ndarray 类型)。
- **index**：数据索引标签，如果不指定，默认从 0 开始。
- **dtype**：数据类型，默认会自己判断。
- **name**：设置名称。
- **copy**：拷贝数据，默认为 False。

### 举例

#### 列表

```python
import pandas as pd
a = [1, 2, 3]
b = ["Google","Runoob","Wiki"]
myvar = pd.Series(a)
myvar1 = pd.Series(b index = ["x", "y", "z"])
print(myvar)
print(myvar[1])
print(myvar1)
print(myvar1["z"]
```

```
0    1
1    2
2    3
dtype: int64
2
x    Google
y    Runoob
z      Wiki
dtype: object
W
```

#### 字典

```python
import pandas as pd
sites = {1: "Google", 2: "Runoob", 3: "Wiki"}
myvar = pd.Series(sites)
myvar1 = pd.Series(sites, index = [1, 2])#导入部分数据
print(myvar)
print(myvar1)
```

```
1    Google
2    Runoob
3      Wiki
dtype: object
1    Google
2    Runoob
dtype: object
```

### more

#### **基本操作：**

```python
# 获取值
value = series[2]  # 获取索引为2的值

# 获取多个值
subset = series[1:4]  # 获取索引为1到3的值

# 使用自定义索引
value = series_with_index['b']  # 获取索引为'b'的值

# 索引和值的对应关系
for index, value in series_with_index.items():
    print(f"Index: {index}, Value: {value}")
```

#### **基本运算：**

```python
# 算术运算
result = series * 2  # 所有元素乘以2

# 过滤
filtered_series = series[series > 2]  # 选择大于2的元素

# 数学函数
import numpy as np
result = np.sqrt(series)  # 对每个元素取平方根
```

#### **属性和方法：**

```python
# 获取索引
index = series_with_index.index

# 获取值数组
values = series_with_index.values

# 获取描述统计信息
stats = series_with_index.describe()

# 获取最大值和最小值的索引
max_index = series_with_index.idxmax()
min_index = series_with_index.idxmin()
```

#### **注意事项：**

- `Series` 中的数据是有序的。
- 可以将 `Series` 视为带有索引的一维数组。
- 索引可以是唯一的，但不是必须的。
- 数据可以是标量、列表、NumPy 数组等。

## DateFrame

 类似于一个二维表格，它是 Pandas 中最重要的数据结构。DataFrame 可以看作是由多个 Series 按列排列构成的表格，它既有行索引也有列索引，因此可以方便地进行行列选择、过滤、合并等操作。

DataFrame 是一个表格型的数据结构，它含有一组有序的列，每列可以是不同的值类型（数值、字符串、布尔型值）。DataFrame 既有行索引也有列索引，它可以被看做由 Series 组成的字典（共同用一个索引）。

### **DataFrame 特点：**

- **列和行：** `DataFrame` 由多个列组成，每一列都有一个名称，可以看作是一个 `Series`。同时，`DataFrame` 有一个行索引，用于标识每一行。
- **二维结构：** `DataFrame` 是一个二维表格，具有行和列。可以将其视为多个 `Series` 对象组成的字典。
- **列的数据类型：** 不同的列可以包含不同的数据类型，例如整数、浮点数、字符串等

![img](https://www.runoob.com/wp-content/uploads/2021/04/pandas-DataStructure.png)

```python
pandas.DataFrame( data, index, columns, dtype, copy)
```

- **data**：一组数据(ndarray、series, map, lists, dict 等类型)。
- **index**：索引值，或者可以称为行标签。
- **columns**：列标签，默认为 RangeIndex (0, 1, 2, …, n) 。
- **dtype**：数据类型。
- **copy**：拷贝数据，默认为 False。

### 举例

#### 列表

```python
import pandas as pd
data = [['Google', 10], ['Runoob', 12], ['Wiki', 13]]
# 创建DataFrame
df = pd.DataFrame(data, columns=['Site', 'Age'])
# 使用astype方法设置每列的数据类型
df['Site'] = df['Site'].astype(str)
df['Age'] = df['Age'].astype(float)

print(df)
```

```
     Site   Age
0  Google  10.0
1  Runoob  12.0
2    Wiki  13.0 
```

#### 字典

```python
import pandas as pd
data = {'Site':['Google', 'Runoob', 'Wiki'], 'Age':[10, 12, 13]}
df = pd.DataFrame(data)
df1 = pd.DataFrame(data)
print (df)
```

```python
import pandas as pd
data = [{'a': 1, 'b': 2},{'a': 5, 'b': 10, 'c': 20}]
df1 = pd.DataFrame(data, index = ["day1", "day2"])
print (df)
#没有对应的部分数据为 NaN。
```

```python
# 返回第一行
print(df.loc[0])
# 返回第二行
print(df.loc[1])
# 返回第一行和第二行
print(df.loc[[0, 1]])
```

```
   a   b     c
0  1   2   NaN
1  5  10  20.0
a    1.0
b    2.0
c    NaN
Name: 0, dtype: float64
a     5.0
b    10.0
c    20.0
Name: 1, dtype: float64
   a   b     c
0  1   2   NaN
1  5  10  20.0
```

```python
print (df1)
# 指定索引
print(df1.loc["day2"])
```

```
      a   b     c
day1  1   2   NaN
day2  5  10  20.0
a     5.0
b    10.0
c    20.0
Name: day2, dtype: float64
```

Pandas 可以使用 **loc** 属性返回指定行的数据，如果没有设置索引，第一行索引为 **0**，第二行索引为 **1**，以此类推：

返回结果其实就是一个 Pandas Series 数据。

也可以返回多行数据，使用 **[[ ... ]]** 格式，**...** 为各行的索引，以逗号隔开：

#### ndarrys

```python
import numpy as np
import pandas as pd
# 创建一个包含网站和年龄的二维ndarray
ndarray_data = np.array([
    ['Google', 10],
    ['Runoob', 12], 
    ['Wiki', 13]])
# 使用DataFrame构造函数创建数据帧
df = pd.DataFrame(ndarray_data, columns=['Site', 'Age'])
# 打印数据帧
print(df)
```

```
#字典和ndarrys一样
     Site Age
0  Google  10
1  Runoob  12
2    Wiki  13
```

### more

#### **基本操作：**

```python
# 获取列
name_column = df['Name']

# 获取行
first_row = df.loc[0]

# 选择多列
subset = df[['Name', 'Age']]

# 过滤行
filtered_rows = df[df['Age'] > 30]
```

#### **属性和方法：**

```python
# 获取列名
columns = df.columns

# 获取形状（行数和列数）
shape = df.shape

# 获取索引
index = df.index

# 获取描述统计信息
stats = df.describe()
```

#### **数据操作：**

```python
# 添加新列
df['Salary'] = [50000, 60000, 70000]

# 删除列
df.drop('City', axis=1, inplace=True)
#axis=0表示行就是删除行，axis=1表示列就是删除列
# 排序
df.sort_values(by='Age', ascending=False, inplace=True)
#ascending默认升序，=flase降序
# 重命名列
df.rename(columns={'Name': 'Full Name'}, inplace=True)
```

pandas 中 inplace 参数在很多函数中都会有，它的作用是：是否在原对象基础上进行修改

 inplace = True：不创建新的对象，直接对原始对象进行修改；

 inplace = False：对数据进行修改，创建并返回新的对象承载其修改结果。

默认是False，即创建新的对象进行修改，原对象不变，和深复制和浅复制有些类似。

#### 从外部数据源：

```python
# 从CSV文件创建 DataFrame
df_csv = pd.read_csv('example.csv')

# 从Excel文件创建 DataFrame
df_excel = pd.read_excel('example.xlsx')

# 从字典列表创建 DataFrame
data_list = [{'Name': 'Alice', 'Age': 25}, {'Name': 'Bob', 'Age': 30}]
df_from_list = pd.DataFrame(data_list)
```

#### **注意事项：**

- `DataFrame` 是一种灵活的数据结构，可以容纳不同数据类型的列。
- 列名和行索引可以是字符串、整数等。
- `DataFrame` 可以通过多种方式进行数据选择、过滤、修改和分析。
- 通过对 `DataFrame` 的操作，可以进行数据清洗、转换、分析和可视化等工作。

## Pandas CSV 文件

```python
import pandas as pd

df = pd.read_csv('nba.csv')

print(df.to_string())
```

**to_string()** 用于返回 DataFrame 类型的数据，如果不使用该函数，则输出结果为数据的前面 5 行和末尾 5 行，中间部分以 **...** 代替。



我们也可以使用 **to_csv()** 方法将 DataFrame 存储为 csv 文件：

```python
import pandas as pd 
# 三个字段 name, site, age
nme = ["Google", "Runoob", "Taobao", "Wiki"]
st = ["www.google.com", "www.runoob.com", "www.taobao.com", "www.wikipedia.org"]
ag = [90, 40, 80, 98]
# 字典
dict = {'name': nme, 'site': st, 'age': ag} 
df = pd.DataFrame(dict)
# 保存 dataframe
df.to_csv('site.csv')
```

### 数据处理

#### head(n)

**head( n)** 方法用于读取前面的 n 行，如果不填参数 n ，默认返回 5 行。

```python
import pandas as pd

df = pd.read_csv('nba.csv')

print(df.head())
```

#### tail(n)

**tail(n)** 方法用于读取尾部的 n 行，如果不填参数 n ，默认返回 5 行，空行各个字段的值返回 **NaN**。

```python
import pandas as pd

df = pd.read_csv('nba.csv')

print(df.tail())
```

#### info()

info() 方法返回表格的一些基本信息

```python
import pandas as pd

df = pd.read_csv('nba.csv')

print(df.info())
```

## Pandas JSON

### json文件

```python
import pandas as pd

df = pd.read_json('sites.json')
   
print(df.to_string())
```

### json数据直接处理

```python
import pandas as pd

data =[
    {
      "id": "A001",
      "name": "菜鸟教程",
      "url": "www.runoob.com",
      "likes": 61
    },
    {
      "id": "A002",
      "name": "Google",
      "url": "www.google.com",
      "likes": 124
    },
    {
      "id": "A003",
      "name": "淘宝",
      "url": "www.taobao.com",
      "likes": 45
    }
]
df = pd.DataFrame(data)

print(df)
```

JSON 对象与 Python 字典具有相同的格式，所以我们可以直接将 Python 字典转化为 DataFrame 数据

### 从 URL 中读取 JSON 数据

```python
import pandas as pd

URL = 'https://static.jyshare.com/download/sites.json'
df = pd.read_json(URL)
print(df)
```

#### 内嵌的 JSON 数据

```json
{
    "school_name": "ABC primary school",
    "class": "Year 1",
    "students": [
    {
        "id": "A001",
        "name": "Tom",
        "math": 60,
        "physics": 66,
        "chemistry": 61
    },
    {
        "id": "A002",
        "name": "James",
        "math": 89,
        "physics": 76,
        "chemistry": 51
    },
    {
        "id": "A003",
        "name": "Jenny",
        "math": 79,
        "physics": 90,
        "chemistry": 78
    }]
}
```

```python
import pandas as pd

df = pd.read_json('nested_list.json')

print(df)
```

**json_normalize()** 方法将内嵌的数据完整的解析出来

```python
import pandas as pd
import json

# 使用 Python JSON 模块载入数据
with open('nested_list.json','r') as f:
    data = json.loads(f.read())

# 展平数据
df_nested_list = pd.json_normalize(data, record_path =['students'])
print(df_nested_list)
```

#### glom！

## Pandas 数据清洗

### Pandas 清洗空值

删除包含空字段的行，可以使用 **dropna()** 方法

```python
DataFrame.dropna(axis=0, how='any', thresh=None, subset=None, inplace=False)
```

- axis：默认为 **0**，表示逢空值剔除整行，如果设置参数 **axis＝1** 表示逢空值去掉整列。
- how：默认为 **'any'** 如果一行（或一列）里任何一个数据有出现 NA 就去掉整行，如果设置 **how='all'** 一行（或列）都是 NA 才去掉这整行。
- thresh：设置需要多少非空值的数据才可以保留下来的。
- subset：设置想要检查的列。如果是多个列，可以使用列名的 list 作为参数。
- inplace：如果设置 True，将计算得到的值直接覆盖之前的值并返回 None，修改的是源数据。

通过 **isnull()** 判断各个单元格是否为空。

```
0      3
1      3
2    NaN
3      1
4      3
5    NaN
6      2
7      1
8     na
Name: NUM_BEDROOMS, dtype: object
0    False
1    False
2     True
3    False
4    False
5     True
6    False
7    False
8    False
Name: NUM_BEDROOMS, dtype: bool
```

 n/a 和 NA 当作空数据，na 不是空数据，不符合要求

```python
df = pd.read_csv('property-data.csv', na_values = missing_values)
#指定空数据类型
```

默认情况下，dropna() 方法返回一个新的 DataFrame，不会修改源数据。

如果你要修改源数据 DataFrame, 可以使用 **inplace = True**

```python
df.dropna(subset=['ST_NUM'], inplace = True)
#移除 ST_NUM 列中字段值为空的行

df.fillna(12345, inplace = True)
# fillna() 方法来替换一些空字段

df['PID'].fillna(12345, inplace = True)
#某一个列来替换数据

x = df["ST_NUM"].mean()
df["ST_NUM"].fillna(x, inplace = True)
#使用 mean() 方法计算列的均值并替换空单元格

x = df["ST_NUM"].median()
df["ST_NUM"].fillna(x, inplace = True)
#使用 median() 方法计算列的中位数并替换空单元格

x = df["ST_NUM"].mode()
df["ST_NUM"].fillna(x, inplace = True）
#使用 mode() 方法计算列的众数并替换空单元格
                    
```

### Pandas 清洗格式错误数据

DataFrame

### Pandas 清洗重复数据

如果我们要清洗重复数据，可以使用 **duplicated()** 和 **drop_duplicates()** 方法。

如果对应的数据是重复的，**duplicated()** 会返回 True，否则返回 False。

```python
import pandas as pd

person = {
  "name": ['Google', 'Runoob', 'Runoob', 'Taobao'],
  "age": [50, 40, 40, 23]  
}
df = pd.DataFrame(person)
print(df.duplicated())
```

```python
import pandas as pd

persons = {
  "name": ['Google', 'Runoob', 'Runoob', 'Taobao'],
  "age": [50, 40, 40, 23]  
}
df = pd.DataFrame(persons)
df.drop_duplicates(inplace = True)
print(df)
```

## Pandas 常用函数

#### 读取数据

| 函数                                  | 说明                       |
| :------------------------------------ | :------------------------- |
| pd.read_csv(filename)                 | 读取 CSV 文件；            |
| pd.read_excel(filename)               | 读取 Excel 文件；          |
| pd.read_sql(query, connection_object) | 从 SQL 数据库读取数据；    |
| pd.read_json(json_string)             | 从 JSON 字符串中读取数据； |
| pd.read_html(url)                     | 从 HTML 页面中读取数据。   |

```python
import pandas as pd

# 从 CSV 文件中读取数据
df = pd.read_csv('data.csv')

# 从 Excel 文件中读取数据
df = pd.read_excel('data.xlsx')

# 从 SQL 数据库中读取数据
import sqlite3
conn = sqlite3.connect('database.db')
df = pd.read_sql('SELECT * FROM table_name', conn)

# 从 JSON 字符串中读取数据
json_string = '{"name": "John", "age": 30, "city": "New York"}'
df = pd.read_json(json_string)

# 从 HTML 页面中读取数据
url = 'https://www.runoob.com'
dfs = pd.read_html(url)
df = dfs[0] # 选择第一个数据框
```

#### 查看数据

| 函数          | 说明                                                       |
| :------------ | :--------------------------------------------------------- |
| df.head(n)    | 显示前 n 行数据；                                          |
| df.tail(n)    | 显示后 n 行数据；                                          |
| df.info()     | 显示数据的信息，包括列名、数据类型、缺失值等；             |
| df.describe() | 显示数据的基本统计信息，包括均值、方差、最大值、最小值等； |
| df.shape      | 显示数据的行数和列数。                                     |

```python
# 显示前五行数据
df.head()

# 显示后五行数据
df.tail()

# 显示数据信息
df.info()

# 显示基本统计信息
df.describe()

# 显示数据的行数和列数
df.shape
```

#### 数据清洗

| 函数                             | 说明                     |
| :------------------------------- | :----------------------- |
| df.dropna()                      | 删除包含缺失值的行或列； |
| df.fillna(value)                 | 将缺失值替换为指定的值； |
| df.replace(old_value, new_value) | 将指定值替换为新值；     |
| df.duplicated()                  | 检查是否有重复的数据；   |
| df.drop_duplicates()             | 删除重复的数据。         |

```python
# 删除包含缺失值的行或列
df.dropna()

# 将缺失值替换为指定的值
df.fillna(0)

# 将指定值替换为新值
df.replace('old_value', 'new_value')

# 检查是否有重复的数据
df.duplicated()

# 删除重复的数据
df.drop_duplicates()
```

#### 数据选择和切片

| 函数                                          | 说明                         |
| :-------------------------------------------- | :--------------------------- |
| df[column_name]                               | 选择指定的列；               |
| df.loc[row_index, column_name]                | 通过标签选择数据；           |
| df.iloc[row_index, column_index]              | 通过位置选择数据；           |
| df.ix[row_index, column_name]                 | 通过标签或位置选择数据；     |
| df.filter(items=[column_name1, column_name2]) | 选择指定的列；               |
| df.filter(regex='regex')                      | 选择列名匹配正则表达式的列； |
| df.sample(n)                                  | 随机选择 n 行数据。          |

```python
# 选择指定的列
df['column_name']

# 通过标签选择数据
df.loc[row_index, column_name]

# 通过位置选择数据
df.iloc[row_index, column_index]

# 通过标签或位置选择数据
df.ix[row_index, column_name]

# 选择指定的列
df.filter(items=['column_name1', 'column_name2'])

# 选择列名匹配正则表达式的列
df.filter(regex='regex')

# 随机选择 n 行数据
df.sample(n=5)
```

#### 数据排序

| 函数                                                         | 说明                 |
| :----------------------------------------------------------- | :------------------- |
| df.sort_values(column_name)                                  | 按照指定列的值排序； |
| df.sort_values([column_name1, column_name2], ascending=[True, False]) | 按照多个列的值排序； |
| df.sort_index()                                              | 按照索引排序。       |

```python
# 按照指定列的值排序
df.sort_values('column_name')

# 按照多个列的值排序
df.sort_values(['column_name1', 'column_name2'], ascending=[True, False])

# 按照索引排序
df.sort_index()
```

#### 数据分组和聚合#

| 函数                                            | 说明                         |
| :---------------------------------------------- | :--------------------------- |
| df.groupby(column_name)                         | 按照指定列进行分组；         |
| df.aggregate(function_name)                     | 对分组后的数据进行聚合操作； |
| df.pivot_table(values, index, columns, aggfunc) | 生成透视表。                 |

```python
# 按照指定列进行分组
df.groupby('column_name')

# 对分组后的数据进行聚合操作
df.aggregate('function_name')

# 生成透视表
df.pivot_table(values='value', index='index_column', columns='column_name', aggfunc='function_name')
```

#### 数据合并#

| 函数                               | 说明                             |
| :--------------------------------- | :------------------------------- |
| pd.concat([df1, df2])              | 将多个数据框按照行或列进行合并； |
| pd.merge(df1, df2, on=column_name) | 按照指定列将两个数据框进行合并。 |

```
# 将多个数据框按照行或列进行合并
df = pd.concat([df1, df2])

# 按照指定列将两个数据框进行合并
df = pd.merge(df1, df2, on='column_name')
```

#### 数据选择和过滤

| 函数                                 | 说明                                   |
| :----------------------------------- | :------------------------------------- |
| df.loc[row_indexer, column_indexer]  | 按标签选择行和列。                     |
| df.iloc[row_indexer, column_indexer] | 按位置选择行和列。                     |
| df[df['column_name'] > value]        | 选择列中满足条件的行。                 |
| df.query('column_name > value')      | 使用字符串表达式选择列中满足条件的行。 |

#### 数据统计和描述

| df.describe() | 计算基本统计信息，如均值、标准差、最小值、最大值等。 |
| ------------- | ---------------------------------------------------- |
| df.mean()     | 计算每列的平均值。                                   |
| df.median()   | 计算每列的中位数。                                   |
| df.mode()     | 计算每列的众数。                                     |
| df.count()    | 计算每列非缺失值的数量。                             |

## Pandas 相关性分析

Pandas 使用 **corr()** 方法计算数据集中每列之间的关系。

```python
df.corr(method='pearson', min_periods=1)
```

- **method** (可选): 字符串类型，用于指定计算相关系数的方法。默认是 'pearson'，还可以选择 'kendall'（Kendall Tau 相关系数）或 'spearman'（Spearman 秩相关系数）。
- **min_periods** (可选): 表示计算相关系数时所需的最小观测值数量。默认值是 1，即只要有至少一个非空值，就会进行计算。如果指定了 `min_periods`，并且在某些列中的非空值数量小于该值，则相应列的相关系数将被设为 NaN

**df.corr()** 方法返回一个相关系数矩阵，矩阵的行和列对应数据框的列名，矩阵的元素是对应列之间的相关系数。

常见的相关性系数包括 Pearson 相关系数和 Spearman 秩相关系数：

- **Pearson 相关系数:** 即皮尔逊相关系数，用于衡量了两个变量之间的线性关系强度和方向。它的取值范围在 -1 到 1 之间，其中 -1 表示完全负相关，1 表示完全正相关，0 表示无线性相关。可以使用 **corr()** 方法计算数据框中各列之间的 Pearson 相关系数。
- **Spearman 相关系数：**即斯皮尔曼相关系数，是一种秩相关系数。用于衡量两个变量之间的单调关系，即不一定是线性关系。它通过比较变量的秩次来计算相关性。可以使用 **corr(method='spearman')** 方法计算数据框中各列之间的 Spearman 相关系数。

```python
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd

# 创建一个示例数据框
data = {'A': [1, 2, 3, 4, 5], 'B': [5, 4, 3, 2, 1]}
df = pd.DataFrame(data)

# 计算 Pearson 相关系数
correlation_matrix = df.corr()
# 使用热图可视化 Pearson 相关系数
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', fmt=".2f")
plt.show()
```

