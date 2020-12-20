# NoSQL 文档存储

### 什么是 NoSQL

- NoSQL是Not Only SQL的简称，意思是“不仅仅是SQL”。 

- 目前，我们常用的都是关系型数据库，如Oracle、DB2、MySQL、SQL Server等。实践证明，关系模型是非常适合于客户服务器编程，它是结构化数据存储在网络和商务应用的主导技术。

- NoSQL，指的是非关系型的数据库，它是对不同于传统的关系型数据库的数据库管理系统的统称。

- NoSQL用于超大规模数据的存储。（例如谷歌或Facebook每天为他们的用户收集万亿比特的数据）。这些类型的数据存储不需要固定的模式，无需多余操作就可以横向扩展。

  ![](Resources/11.jpg)

## NoSQL数据库的分类

从网站 http://nosql-database.org/ 可以了解到，NoSQL数据库目前有200多种。这些NoSQL数据库大体上可以分为四类：键值存储、列存储、文档存储和图形存储。

![](Resources/12.jpg)

## MySQL的文档存储

在关系数据库中，需要先定义表才能存储数据。

文档存储更加灵活，不需要事先定义数据结构、数据约束等就可以直接存储数据。

将MySQL用作文档存储时，集合是容器，集合包含可以添加、查找、更新和删除的JSON文档。

![](Resources/13.jpg)

![](Resources/14.jpg)

## 文档存储的基本使用

```mysql
#使用MySQL Shell连接数据库（支持文档存储）
mysqlsh root@localhost:33060/mydb

#查看当前数据库
db

#查看当前数据库有哪些集合
db.getCollections()

#创建集合
db.createCollection("employee_ds")

#删除集合
db.dropCollection("employee_ds")

#添加文档
db.employee_ds.add({
    "id":1,
    "name":"张三",
    "sex":"男",
    "salary":5500,
    "dept":"部门A"
})

#查询文档
# 1. 无参数时类似于 SELECT * FROM table;
# 2. 有参数时类似于 SELECT * FROM table WHERE ....
db.employee_doc.find("name='柳峰'")

#删除文档
db.employee_doc.remove("name='柳峰'")

#删除所有文档
db.employee_doc.remove("true")
```

## 例子

- Setp 1：连接数据库

  ![](Resources/15.jpg)

- Step 2：查看当前数据库、当前数据库中有哪些集合、并创建集合 employee_ds

  ![](Resources/16.jpg)

- Step 3：创建两个文档，并检索

  ![](Resources/17.jpg)

  ![](Resources/18.jpg)

- Step 4: 删除文档，并查看结果

  ![](Resources/19.jpg)

- Step 5： 删除所有文档，并查看结果

  ![](Resources/20.jpg)