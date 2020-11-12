# DISTINCT 去除重复数据



### 说明

> **distinct 用于在查询中返回列的唯一不同值（去除重复），支持单列或多列。**
>
> **在实际的应用中，表中的某一列含有重复值是很常见的，如 employ 表的 dept 列。**
>
> **如果在查询数据时，希望得到某列的所有不同值，可以使用 dinstinct。**

### 语法

```mysql
SELECT DISTINCT comlumn_name1, column_name2
FROM table_name;
```

说明：

- DISTINCT ：作用于后面所有的字段，即多字段的情况下，当多字段都相同时，才会被去重.

例子：对表 footprint 中的 username 去重查询

<img src="Resources/61.jpg"/>

### 例子

- 打印已有的 employee 表

  <img src="Resources/62.jpg"/>

- 性别去重

  ```mysql
  select distinct sex from employee;
  ```

  <img src="Resources/63.jpg"/>

- 部门去重

  ```mysql
  select distinct dept from employee;
  ```

  <img src="Resources/64.jpg"/>

- 创建并打印 footprint 表

  <img src="Resources/65.jpg"/>

<img src="Resources/66.jpg"/>

- 对 username 字段去重

  ```mysql
  select distinct username from footprint;
  ```

  <img src="Resources/67.jpg"/>

- 对 city 字段去重

  ```mysql
  select distinct city from footprint;
  ```

  <img src="Resources/68.jpg"/>

- 对 username、city 字段都相同的数据 去重

  ```mysql
  select distinct username, city from footprint;
  ```

  

  <img src="Resources/69.jpg"/>