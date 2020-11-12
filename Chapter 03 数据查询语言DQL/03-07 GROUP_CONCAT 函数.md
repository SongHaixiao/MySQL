# GROUP_CONCAT 函数

### 应用场景

使用 group by 可以分组统计每个部门有多少员工。

假如，除了统计每个部门的员工数量之外，还想知道具体是哪些员工（员工列表），又该如何实现呢？

<img src="Resources/54.jpg"/>

### 说明

group_concat 配合 group by 一起使用，用于将 