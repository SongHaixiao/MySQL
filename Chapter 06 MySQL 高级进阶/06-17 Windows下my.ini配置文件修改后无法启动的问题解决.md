



# *Windows下my.ini配置文件修改后无法启动的问题解决**

### 如何解决my.ini修改后无法启动的问题

在Windows中，修改了MySQL 8.0的配置文件my.ini后会发现启动MySQL失败，错误提示如下。

![](Resources/116.jpg)

在Windows中，MySQL配置文件的编码为ANSI，但是修改配置文件后默认保存的编码为UTF-8，

这会导致MySQL解析配置文件错误，无法启动。只需要将配置文件另存为ANSI编码即可。

![](Resources/117.jpg)

### 例子

- 在 Dos 中启动 MySQL,可以启动

  ![](Resources/121.jpg)

- 找到 my.ini 数据库配置文件

  ![](Resources/118.jpg)

  ![](Resources/119.jpg)

- 不做任何操作，仅仅保存 my.ini 文件，然后启动 Dos 执行，然后无法启动

  ![](Resources/120.jpg)

  `Tip：可以把 my.ini 文件复制后再修改，因为 把复制后的 my.ini在复制回来，相当于把原 my.ini 文件复制回来，my.ini 等于没有改变，依旧可以运行，这样做可以做一个保底。`



- 修改 my.ini 格式 为 ANSI  格式

  <img src="Resources/122.jpg" style="zoom:50%;" />

- 再次启动，发现可以启动

  <img src="Resources/123.jpg" style="zoom:100%;" />