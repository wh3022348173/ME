# 介绍

1. 数据库是什么？有什么作用呢？

数据库就是指数据存储的库，作用就是组织数据并存储数据。

2. 数据库如何组织数据呢？

按照：库 -> 表 -> 数据 三个层级进行组织

3. 数据库软件是什么？我们学习哪种数据库软件呢？

数据库软件就是提供库->表->数据，这种数据组织形式的工具软件，也称之为数据库管理系统

常见的数据库软件有：Oracle、MySQL、SQL Server、PostgreSQL、SQLite，课程以MySQL软件为基础进行学习

4. 数据库和SQL的关系是？

数据库（软件）提供数据组织存储的能力

SQL语句则是操作数据、数据库的工具语言

### **SQL**语言的分类

#### •数据定义：DDL（Data Definition Language）

•库的创建删除、表的创建删除等

#### •数据操纵：DML（Data Manipulation Language）

•新增数据、删除数据、修改数据等

#### •数据控制：DCL（Data Control Language）

•新增用户、删除用户、密码修改、权限管理等

#### •数据查询：DQL（Data Query Language）

•基于需求查询和计算数据

### **SQL**的语法特征

•SQL语言，大小写不敏感

•SQL可以单行或多行书写，最后以;号结束

•SQL支持注释：

•单行注释： -- 注释内容（--后面一定要有一个空格）

•单行注释：# 注释内容（# 后面可以不加空格，推荐加上）

•多行注释：/* 注释内容 */

## DDL

### DDL- 库管理

```sql
SHOW DATABASE;  #查看数据库
USE 数据库名称；#使用数据库
CREATE DATABASE 数据库名称 [CHARSET UTF8]; #创建数据库
DROP DATABASE 数据据名称；#删除数据库
SELECT DATABASE();#查看当前使用的数据库
```

### DDL- 表管理

```sql
SHOW TABLES;#查看有哪些表
DROP TABLE 表名称；
DROP TABLE IF EXISTS 表名称；#删除表
CREATE TABLE 表名称(
	列名称，列类型，
	列名称，列类型，
	列名称，列类型，
    ......
); #创建表

int -- 整形
float -- 浮点数
varchar(长度) -- 文本，长度为数字，做最大长度限制
date -- 日期类型
timestamp -- 时间戳类型


```

## DML

DML是指数据操作语言，英文全称是Data Manipulation Language，用来对数据库中表的数据记录进行更新。

**数据插入** **INSERT**

```sql
INSERT INTO 表[(列1，列2，列N)] VALUES(值1，值2，值N)[，(值1，值2，值N),(值1，值2，值N)......]
```

**数据删除** **DELETE**

```sql
DELETE FROM 表名称 [WHERE 条件判断]
/* = > < >= <= != */
```

**数据更新** **UPDATE**

```sql
UPDATE 表名 SET 列=值 [WHERE 条件判断]
```

## DQL

**基础数据查询**

在SQL中，通过SELECT关键字开头的SQL语句，来进行数据的查询

```SQL
SELECT 字段列表|* FROM 表
#从（FROM）表中，选择（SELECT）某些列进行展示
SELECT 字段列表|* FROM 表 WHERE 条件判断
```

### 分组聚合

```sql
SELECT 字段|聚合函数 FROM 表 [WHILE 条件判断] GROUP BY 列
SUM(列) -- 求和
AVG(列) -- 求平均值
MIN(列) -- 求最小值
MAX(列) -- 求最大值
COUNT(列|*) -- 求数量

```

**结果排序**

可以对查询的结果，使用ORDER BY 关键字，指定某个列进行排序

```sql
SELECT 字段|聚合函数|* FROM 表 
WHERE ...
GROUP BY ...
ORDER BY ...[ASC|DESC]
```

同样，可以使用LIMIT关键字，对查询结果进行数量限制或分页显示

```sql
SELECT 字段|聚合函数|* FROM 表 
WHERE ...
GROUP BY ...
ORDER BY ...[ASC|DESC]
LIMIT n[,m]
```

#### 注意

•WHERE、GROUP BY、ORDER BY、 LIMIT均可按需求省略

•SELECT 和 FROM 是必写的

•执行顺序：

**FROM -> WHERE -> GROUP BY****和聚合函数** **-> SELECT -> ORDER BY -> LIMIT**

## pymysql

如何获取链接对象？

•from pymysql import Connection 导包

•Connection(主机,端口,账户,密码)即可得到链接对象

•链接对象.close() 关闭和MySQL数据库的连接

如何执行SQL查询

通过连接对象调用cursor()方法，得到游标对象

•游标对象.execute()执行SQL语句

•游标对象.fetchall()得到全部的查询结果封装入元组内

```python
from pymysql import Connection

# 构建到MySQL数据库的链接
conn = Connection(
    host="localhost",   # 主机名（IP）
    port=3306,          # 端口
    user="root",        # 账户
    password="wen123",  # 密码
    autocommit=True     # 设置自动提交
)

print(conn.get_server_info())
# 执行非查询性质SQL
cursor = conn.cursor()      # 获取到游标对象
# # 选择数据库
conn.select_db("bear")
# # 执行sql
cursor.execute("DELETE FROM student WHERE id >10020 ")
# # 关闭链接
```

