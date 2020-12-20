# Navicat无法连接MySQL 8.0的问题解决

## Navicat无法连接MySQL 8.0的问题解决

## 问题

老版本的Navicat连接能正常连接MySQL 5.x，但是连接MySQL 8.0却报错，错误提示如图所示。

<img src="Resources/01.jpg" style="zoom:80%;" />

​	*Client does not support authentication protocol requested by server;consider upgrading MySQL client*

​	*客户端不支持服务器请求的身份验证协议；请考虑升级MySQL客户端*

## 解决

MySQL 5.x的身份认证方式为 mysql_native_password，也就是Navicat客户端支持的认证方式。

但是MySQL 8.0升级了身份认证方式，默认为 caching_sha2_password。因此，在不升级Navicat

版本的情况下，可以将MySQL 8.0的身份认证方式修改为 mysql_native_password。

```mysql
# 更改数据库密码认证方式
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '123456';

# 刷新权限
FLUSH PRIVILEGES;
```

## 例子

- 通过右键查看连接信息

  <img src="Resources/21.jpg" style="zoom:70%;" />

<img src="Resources/22.jpg" style="zoom:70%;" />

- 双击 本地主机 MySQL

  <img src="Resources/23.jpg" style="zoom:70%;" />

- 通过 Dos 进入 mysql,并更改 密码认证方式

  <img src="Resources/24.jpg" style="zoom:70%;" />

- 双击 本机MySQL 可以进入

  <img src="Resources/25.jpg" style="zoom:70%;" />