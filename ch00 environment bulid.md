# 第0章：环境搭建

# 本章重点:
* 在电脑上安装MySQL数据库系统
* 安装客户端并连接到本机上的MySQL数据库
* 使用提供的脚本创建本教程所使用的示例数据库
# 1. MySQL 8.0 的安装

考虑到大家所使用的操作系统的不同,  本教程分别提供了 windows 10, macOS和centos平台上的MySQL 8.0 的安装流程, 你可根据自己所使用电脑的操作系统选择以下三节中的一节进行学习和安装.

## 1.1 windows 下 MySQL 8.0 的下载安装

首先以最常见的 win10 为例, 介绍 MySQL8.0 的下载安装.

### 1.1.1 下载

MySQL 针对个人用户和商业用户提供了不同的版本, MySQL 社区版(MySQL Community Edition) 是供个人用户免费下载的开源数据库, 本教程将以MySQL 社区版为例进行安装连接和SQL查询的讲解.

MySQL 官网上的社区版软件的下载地址[https://dev.mysql.com/downloads/](https://dev.mysql.com/downloads/), 选择[MySQL Installer for Windows](https://dev.mysql.com/downloads/windows/)可以下载 windows 操作系统下的最新版 MySQL安装文件. 如果需要安装历史版本, 可以选择最后的[Download Archives](https://downloads.mysql.com/archives/)后选择[MySQL Installer](https://downloads.mysql.com/archives/installer/),然后在新页面里选择所需历史版本的社区版.

如果想下载本教程所使用的 MySQL 8.0.21.0, 也可以在百度⽹盘下载, 

下载链接：[https://pan.baidu.com/s/1SOtMoVqqRXwa2qD0siHcIg](https://pan.baidu.com/s/1SOtMoVqqRXwa2qD0siHcIg)提取码：80lf

备用下载链接：[https://pan.baidu.com/s/1zK2vj50DvuAee-EqAcl-0A](https://pan.baidu.com/s/1zK2vj50DvuAee-EqAcl-0A)提取码：80lf

我们接下来以文档写作时的最新版 MySQL 8.0.21 为例, 进行下载安装的介绍.

进入到[MySQL Installer for Windows](https://dev.mysql.com/downloads/windows/)页面后, 选择下载下方的完整安装程序.

![图片](./img/ch00/ch0001.png)

在下载页面选择下方的不注册,仅下载.

![图片](./img/ch00/ch0002.png)

完成下载后, 得到一个后缀为msi的安装文件.

![图片](./img/ch00/ch0003.png)

### 1.1.2 安装

找到刚才下载好的msi文件, 双击开始安装. 初学者建议采用完全安装模式(Full)进行安装:

![图片](./img/ch00/ch0004.png)

选择安装路径和数据存放路径, 二者都可以选择在非系统盘(注意要点击最右侧的按钮进行选择, 不要直接在文本框中修改安装路径).

![图片](./img/ch00/ch0005.png)

完全安装模式下, 部分模块会依赖其他其他组件(每台电脑上列出的依赖项很可能会有不同).

![图片](./img/ch00/ch0006.png)

如果你的电脑之前没有安装过这些组件, 则需要额外进行安装, 此处点击 Execute 按钮即可:

![图片](./img/ch00/ch0007.png)

在这些所依赖的组件的安装过程中, 只需要一路选择"同意"并逐个安装就可以了:

![图片](./img/ch00/ch0008.png)

安装好⼀个组件后, 点击关闭按钮, ⾃动开始安装下⼀个组件(这一步根据操作系统版本可能会略有不同)

![图片](./img/ch00/ch0009.png)

![图片](./img/ch00/ch0010.png)

![图片](./img/ch00/ch0011.png)

正常情况下,会将所有组件安装成功.但可能会有个别组件未安装成功. 个别组件没有呈现绿⾊是因为你的电脑中缺少某个程序, 例如, 如果你的电脑没有安装 Python 环境, 则该项目就不会呈现绿色. 待下边剩下 3 个按钮且上⽅⼤部分组件为绿色时, 即可点击 Next:

![图片](./img/ch00/ch0012.png)

如果有个别组件未安装成功, 此时可以先选择 Yes, 忽略个别组件的安装.

![图片](./img/ch00/ch0013.png)

点击 Excute, 开始安装服务器软件MySQL Server, 连接和查询软件MySQL Workbench及其他相关软件等内容.

![图片](./img/ch00/ch0014.png)

稍等片刻,  安装完成后, 点击 Next

![图片](./img/ch00/ch0015.png)

![图片](./img/ch00/ch0016.png)

下图这一步是选是否以集群方式安装 MySQL, 我们选择默认的第一个, 然后点击 Next:

![图片](./img/ch00/ch0017.png)

此处上边的各种相关配置保持默认即可,**勾选最下边的"Show Advanced and Logging Options"框,**然后点击 Next:

![图片](./img/ch00/ch0018.png)

下图是密码强度的设置, 第⼀种模式为强密码校验模式, MySQL 8.0 推荐使⽤最新的数据库和客户端, 更换了加密插件, 者可能导致第三⽅客户端⼯具⽆法连接数据库.

第⼆种加密⽅式沿袭了 MySQL 5.x 的加密⽅式, 对第三⽅⼯具连接不敏感, 我们仅为了学习 SQL 查询, 并不需要很高的安全性, 因此此处请务必选择第二种⽅式(非常重要):

![图片](./img/ch00/ch0019.png)

在这一步设置 MySQL 的 root 账户密码, 由于上一步选择了第二个选项, 因此这里可以设置为较简单容易记忆的而密码, 例如"123456". 建议设置⽐较简单的密码, 并将密码记录下来以防遗忘, 忘记密码是⼀件麻烦事.

![图片](./img/ch00/ch0020.png)

此处保持默认即可, 如果 windows service name 右侧有⻩⾊警告图标显示, 表示名称重复, ⼿动更换⼀个名称即可, 然后点击 Next:

![图片](./img/ch00/ch0021.png)

Logging Options 这里使用默认设置即可, 我们的学习中暂时用不到这些设置, 直接点击 Next:

![图片](./img/ch00/ch0022.png)

下图是设置是否大小写敏感的. 这一步非常重要,**由于windows系统是大小写不敏感的, 请大家务必使用第一个选项Lower Case**.

![图片](./img/ch00/ch0023.png)

点击 Execute

![图片](./img/ch00/ch0024.png)

完成安装后, 在下图中点击 Finish 回到安装的主进程:

![图片](./img/ch00/ch0025.png)

在主进程界面点击 Next

![图片](./img/ch00/ch0026.png)

这一步无需任何选择, 直接点击 Finish

![图片](./img/ch00/ch0027.png)

进入到 Connect To Server 界面后, 输⼊刚才设置的密码, 点击 check 进⾏校验, 校验通过后 Status 会显示连接成功, 然后点击 Next

![图片](./img/ch00/ch0028.png)

点击 Excute 应用设置:

![图片](./img/ch00/ch0029.png)

上述步骤完成后, 点击 Finish

![图片](./img/ch00/ch0030.png)

回到安装主进程后, 点击 Next

![图片](./img/ch00/ch0031.png)

点击 Finish,完成安装.

![图片](./img/ch00/ch0032.png)

现在, 你的电脑上就已经安装了MySQL的服务器软件, 用于连接服务器进行查询的MySQL Workbench, 以及其他程序语言连接MySQL的驱动, 此外还安装了几个示例数据库, 但本教程将采用<SQL基础教程>一书中的示例数据库, 该数据库的创建和数据导入将在本章第三节介绍.


## 1.2 macOS 下 MySQL 8.0 的下载安装

MySQL 官网上社区版软件的下载地址[https://dev.mysql.com/downloads/](https://dev.mysql.com/downloads/), 选择[MySQL Community Server](https://dev.mysql.com/downloads/mysql/)可以进一步选择下载 macOS操作系统下的最新版 MySQL. 如果需要安装历史版本, 可以选择最后的[Download Archives](https://downloads.mysql.com/archives/)后选择[MySQL Installer](https://downloads.mysql.com/archives/installer/),然后在新页面里选择所需历史版本的社区版.

![图片](./img/ch00/ch0033.png)

然后选择下载dmg安装文件.

![图片](./img/ch00/ch0034.png)

点击下方的直接下载.

![图片](./img/ch00/ch0035.png)

下载的文件为:

![图片](./img/ch00/ch0036.png)

如果官网下载速度很慢, 或者希望下载本教程所使用的 MySQL 8.0.21.0, 也可以在百度⽹盘下载, 

下载链接：[https://pan.baidu.com/s/1ka22UtzqFdOaIosrpKz92w](https://pan.baidu.com/s/1ka22UtzqFdOaIosrpKz92w)提取码: 8xh4

备用下载链接：[https://pan.baidu.com/s/1XeA_8PQvvRePEdZ5ayOT-Q](https://pan.baidu.com/s/1XeA_8PQvvRePEdZ5ayOT-Q)提取码：8xh4


我们接下来以文档写作时的最新版为 8.0.21 为例, 进行下载安装讲解.

在mac上直接双击dmg文件就可以开始安装了. 我们只选择了安装MySQL Community Server, 因此安装过程较为简单.

![图片](./img/ch00/ch0037.png)

![图片](./img/ch00/ch0038.png)

![图片](./img/ch00/ch0039.png)

注意, 在配置MySQL服务器这一步, 最好选择下边的选项, 这样就可以使用简单密码.

![图片](./img/ch00/ch0040.png)

在 Configuration 接下来的步骤需要设置密码, 如果上一步选择了第二个选项, 这里就可以使用比较简单的密码. 请务必牢记自己设置的密码.

![图片](./img/ch00/ch0041.png)

注意, 如果在前一步选择使用了MySQL8.0强密码, MySQL安装过程中会自动生成一个随机密码, 类似于下图这种形式:

![图片](./img/ch00/ch0042.png)

此时请截图保留该密码, 并在安装完成后, 使用该密码登录并重新设置密码. 由于选择使用了强密码, 此时设置密码必须使用大小写字母数字和特殊符号的组合.

完成安装后, 打开电脑的系统偏好设置, 会出现MySQL的服务标识.

![图片](./img/ch00/ch0043.png)

正确安装MySQL后, 打开上述截图中的MySQL之后会看到如下界面, 在这里可以启动和停止MySQL服务, 以及配置MySQL是否随电脑启动而自动启动.

![图片](./img/ch00/ch0044.png)

安装之后, 如果我们直接在终端输入mysql, 会提示找不到命令, 需要配置一下环境变量才可以, 输入以下命令:

```plain
PATH="$PATH":/usr/local/mysql/bin
```
再通过终端输入mysql登录命令后, 就可以看到mysql的交互式界面了.
![图片](./img/ch00/ch0045.png)

然后输入以下内容, 将自己电脑的mysql路径配置到环境变量中, 如果在安装过程中你没修改过安装路径, 那么你的电脑上MySQL的路径应该和下述代码中所使用的路径是一致的:

```plain
export PATH=$PATH:/usr/local/mysql/bin
```
![图片](./img/ch00/ch0046.png)

运行上述配置后, 通过输入下面这条命令使修改生效

```plain
source ~/.bash_profile
```
接下来, 在你的终端中输入命令来登录到MySQL
```plain
mysql -u root -p
```
然后需要输入你刚才设置的密码(如果你选择了强密码, 则这里需要输入你查到的随机密码), 如果看到以下界面, 则表示你的电脑上: 1.MySQL8.0已经正确安装, 2.已经正确配置了MySQL8.0的环境变量,并且3.已经启动MySQL服务器程序. 如果并没有出现下属界面, 请按照上述三个顺序逐个检查.

![图片](./img/ch00/ch0047.png)

使用终端(或者windows下的命令行)与MySQL进行交互是非常便捷和高效的, 但是对于平时不怎么使用终端的普通人来说, 使用终端在做数据查询时, 在查询结果的显示和导出方面有诸多不便, 特别是当我们对 SQL 查询不熟练的时候, 这种方式很不利于我们进行查询语句的调试. 因此本教程将选择查询界面更加友好的客户端工具来连接数据库, 这种通过终端连接MySQL的方式暂时不再使用.

接下来请安装跳转到2.1节安装MySQL Workbench并连接本机的MySQL服务.

>注:
>macOS上的SQL查询工具也有很多其他的选择, 比如DBeaver(开源, 免费), DataGrip(需付费购买,提供30天的免费试用期, 学生使用学校的邮箱可以申请到一年的免费使用权)等,可参考知乎上的问题 :
>Mac平台上有哪些好的SQL 数据库开发工具？[https://www.zhihu.com/question/20498949](https://www.zhihu.com/question/20498949)
## 


![图片](./img/ch00/ch0048.png)


## 1.3 Linux 下 MySQL 8.0 的下载安装

本节我们以 centos 版本的 Linux 操作系统为例, 介绍下载安装 MySQL8.0.21 的过程. 示例操作系统的linux 版本：centos-release-7-7.1908.0.el7.centos.x86_64

在 CentOS 系统中默认是安装了 MariaDB 的, 但是我们需要的是 MySQL, 我们可以直接下载安装 MySQL, 安装 MySQL 可以覆盖 MariaDB.

>关于 MariaDB:
>MariaDB 数据库管理系统是 MySQL 的一个分支, 主要由开源社区在维护, 采用 GPL 授权许可. 开发这个分支的原因之一是：甲骨文公司收购了 MySQL 后, 有将 MySQL 闭源的潜在风险, 因此社区采用分支的方式来避开这个风险. MariaDB 的目的是完全兼容 MySQL, 包括 API 和命令行, 使之能轻松成为 MySQL 的代替品. 但在两个分支经过了几年的各自迭代之后, 在一些方面二者出现了一些差异.
### 
### 1.3.1 安装步骤:

首先, 从[MySQL官网](https://dev.mysql.com/downloads/repo/yum/)下载 MySQL 的 Yum Repository. 根据 CentOS 和 MySQL 的版本,选择下载相对应的文件. 本文选择红色方框的文件.

![图片](./img/ch00/ch0049.png)

Yum 是一个基于 rpm 的软件包管理器, 它可以从指定的服务器自动下载 RPM 包并且安装, 可以自动处理依赖性关系, 并且一次安装所有依赖的软体包, 无须繁琐地一次次下载、安装.

下载命令：

```plain
wget https://dev.mysql.com/get/mysql80-community-release-el7-2.noarch.rpm
```
用 yum 命令安装下载好的 rpm 包.
```plain
yum -y install mysql80-community-release-el7-2.noarch.rpm
```
安装 MySQL 服务器.
```plain
yum -y install mysql-community-server
```
这一步由于要下载安装文件, 可能会花一些时间.  安装完成后就会覆盖掉之前的 mariadb.
当出现如下图所示的内容,则代表 MySQL 就安装完成了.

![图片](./img/ch00/ch0050.png)

### 1.3.2 MySQL 数据库设置

启动 MySQL

```plain
systemctl start  mysqld.service
```
查看 MySQL 运行状态, Active 后面的状态代表启功服务后为 active (running), 停止后为 inactive (dead), 运行状态如图：
```plain
systemctl status mysqld.service
```
![图片](./img/ch00/ch0051.png)

重新启动 Mysql 和停止 Mysql 的命令如下：

```plain
service mysqld restart  #重新启动 Mysql
systemctl stop mysqld.service   #停止 Mysql
```
此时 MySQL 已经开始正常运行, 不过要想进入 MySQL 还得先找出此时 root 用户的密码, 通过如下命令可以在日志文件中找出密码：
为了加强安全性, MySQL8.0 为 root 用户随机生成了一个密码, 在 error log 中, 关于 error log 的位置, 如果安装的是 RPM 包, 则默认是/var/log/mysqld.log.  只有启动过一次 mysql 才可以查看临时密码

使用命令:

```plain
grep 'temporary password' /var/log/mysqld.log
```
查看初始的随机密码:
![图片](./img/ch00/ch0052.png)

登录 root 用户

```plain
mysql -u root -p
```
然后输入上述查到的初始密码. 登录后还不能做任何查询或建库操作, 因为 MySQL 默认必须修改初始的随机密码之后才能操作数据库,否则会报错:

![图片](./img/ch00/ch0053.png)

修改密码为"123456", 注意结尾要有分号, 表示语句的结束.

```plain
ALTER USER 'root'@'localhost' IDENTIFIED BY '123456';
```
这里有个问题, 新密码设置的时候如果设置的过于简单会报错：

![图片](./img/ch00/ch0054.png)

原因是因为 MySQL 有密码设置的规范, 具体是与 validate_password_policy 的值有关：

![图片](./img/ch00/ch00541.png)

MySQL 完整的初始密码规则可以通过如下命令查看：

![图片](./img/ch00/ch0055.png)

密码的长度是由 validate_password_length 决定的, 而 validate_password_length 的计算公式是：

```plain
validate_password_length = validate_password_number_count + validate_password_special_char_count + (2 * validate_password_mixed_case_count)
```
如果想要设置简单的密码必须要修改约束, 修改两个全局参数：
* **validate_password_policy**代表密码策略, 默认是 1：符合长度, 且必须含有数字, 小写或大写字母, 特殊字符. 设置为 0 判断密码的标准就基于密码的长度了. 一定要先修改两个参数再修改密码
```plain
mysql> set global validate_password.policy=0;
```
* **validate_password_length**代表密码长度, 最小值为 4
```plain
mysql> set global validate_password.length=4; 
```
修改完,如图

![图片](./img/ch00/ch0056.png)

此时密码就可以设置的很简单, 例如 1234 之类的. 到此数据库的密码设置就完成了.

但此时还有一个问题, 就是因为安装了 Yum Repository, 以后每次 yum 操作都会自动更新, 如不需要更新, 可以把这个 yum 卸载掉：

```plain
[root@localhost ~]# yum -y remove mysql80-community-release-el7-2.noarch
```

在 CentOS 中 MySQL 的主要配置所在的目录：

```plain
1 /etc/my.cnf 这是 mysql 的主配置文件
2 /var/lib/mysql mysql 数据库的数据库文件存放位置
3 /var/log mysql 数据库的日志输出存放位置
```
一些可能会用到的设置:

设置表名为大小写不敏感:

1.用root帐号登录后, 使用命令

```plain
systemctl stop mysqld.service
```
停止MySQL数据库服务，修改vi /etc/my.cnf，在[mysqld]下面添加
```plain
 lower_case_table_names=1
```
这里的参数  0 表示区分大小写，1 表示不区分大小写.
2.做好数据备份，然后使用下述命令删除数据库数据(删除后, 数据库将恢复到刚安装的状态)

```plain
rm -rf /var/lib/mysql
```
3.重启数据库 ,此时数据库恢复到初始状态.
```plain
service mysql start
```
4.重复安装时的操作, 查找临时密码
```plain
grep 'temporary password' /var/log/mysqld.log
```
5.修改密码. 密码8位以上, 大小写符号数据. 如想要使用简单密码, 需按照上述安装流程中的步骤进行操作.
```plain
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '****';update user set host = "%" where user='root';
```
6.刷新MySQL的系统权限相关表
```plain
FLUSH PRIVILEGES;
```
此时, MySQL的表名的大小写不再敏感.
### 1.3.3 设置远程连接:

如果你想要在另外一台电脑上连接 centos 上安装的 MySQL, 那么还需要一些其他的设置.

首先需要将 MySQL 设置为可以远程连接，设置 mysql 库的 user 表中帐号的 host 为%, %表示可以从任意 ip 连接 mysql, 为了安全性, 也可以设置为你自己所用于连接 centos 上 MySQL 的电脑所使用的 IP.

其次, MYSQL 8.0 内新增加 mysql_native_password 函数，通过更改这个函数密码来进行远程连接.

例如，更改 root 用户的 native_password 密码

```plain
ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY'MyPass@123';
```
接下来为 centos 的防火墙开启 MySQL 所使用的 3306 端口,并重新加载防火墙:
```plain
firewall-cmd --zone=public --add-port=3306/tcp --permanent
firewall-cmd --reload
```
完成上述设置后, 重新启动 MySQL 服务:
```plain
service mysqld restart  #重新启动 Mysql
```
最后, 在另外一台电脑上, 使用下一节介绍的各类客户端工具进行连接测试.
# 2. 连接 MySQL 并执行 SQL 查询

在安装成功MySQL后, 我们可以通过开始菜单->控制面板->管理工具->服务中查找并开启或关闭MySQL服务. 开启服务后, MySQL Server将以后台服务的形式在你的电脑上运行. 如果想要进行查询, 还需要使用命令行工具或者其他更加友好的应用程序连接到MySQL服务.

## 
## 2.0 使用命令行方式连接MySQL服务

连接数据库的最基本的⽅式, 是使用命令⾏. 以win10为例, 在完成 MySQL 服务的安装后, 在开始菜单找到刚才安装好的 MySQL 8.0 命令⾏⼯具,单击即可打开:

![图片](./img/ch00/ch0057.png)

输⼊你在安装过程中为root用户设置的密码即可连接到数据库, 看到如下界⾯, 表示数据库安装成功,并且你已经使用命令行连接到了数据库(图中红框表示数据库版本), 在最后的 "mysql>" 后即可输入SQL命令执行各种数据库操作.

![图片](./img/ch00/ch0058.png)

但是使用命令行在做数据查询时, 在查询结果的显示和导出方面有诸多不便, 特别是当我们对 SQL 查询不熟练的时候, 这种方式不利于我们进行查询语句的修改和调试. 因此本教程将选择查询界面更加友好的客户端工具(使用MySQL Workbench)来连接数据库, 这种通过命令行连接的方式暂时不再使用.

>常见的可用于连接MySQL数据库并进行查询等操作的管理工具包括开源软件 MySQL Workbench, HeidiSQL和DBeaver, 以及商业软件Navicat(有免费版和14天试用版),SQLyog(有免费的社区版)和DataGrip等等.
## 
## 2.1 使用 MySQL Workbench 连接 MySQL

MySQL Workbench 是 MySQL 官方的客户端工具, 支持windows, macOS和Linux. 对于windows用户, 我们在安装 MySQL 的时候由于选择的是完整安装模式, 因此也同时安装了这个工具, 对于macOS的用户, 可以在[https://dev.mysql.com/downloads/workbench/](https://dev.mysql.com/downloads/workbench/)选择macOS版本进行下载安装. MySQL Workbench 是一款功能强大的数据库管理工具, 它既可以用于设计数据库, 也可以用于连接数据库进行查询, 我们这个课程主要使用它的连接数据库进行查询的功能.

如果你使用的是windows 7 操作系统, 打开 MySQL Workbench 后, 会有如下提示:

![图片](./img/ch00/ch0059.png)

这是说 MySQL 不再维护win7系统下的MySQL Workbench, 但并不影响使用. 打开MySQL Workbench后, 使用快捷键 ctrl+u,或者点击菜单栏里的 Database->Connect to Database, 进入数据库连接的设置界面, 如下图所示:

![图片](./img/ch00/ch0060.png)

然后如下图红框中设置连接本机的 MySQL8.0, 输入密码并点击 OK:

![图片](./img/ch00/ch0061.png)

如果弹出如下对话框,表示 MySQL 服务器设置为对于表名和列名的大小写敏感, 但由于 windows 系统默认的是大小写不敏感, 因此当表名或列名有大写字母时, 即使写的 SELECT 语句中正确地使用了大写的表名, 程序也无法正确执行. 这时候建议大家在开始学习查询之前,把表名逐一更改为小写.

![图片](./img/ch00/ch0062.png)

打开后的界⾯

![图片](./img/ch00/ch0063.png)

在中间的编辑器里, 就可以写 SQL 查询了.

下一次打开软件时, 可以直接点击保存的数据库连接, 不需要先进行设置后再连接了:

![图片](./img/ch00/ch0064.png)

## 2.2 [选学]使用 HeidiSQL 连接 MySQL

HeidiSQL 是一款功能非常强大的开源免费的数据库客户端软件, 采用 Delphi 语言开发, 支持 Windows 操作系统. 支持 MySQL、Postgresql、MariaDB、Percona Server 和微软的 SQL Server, 官网下载地址:[https://www.heidisql.com/download.php](https://www.heidisql.com/download.php), 下载 portable 版本后, 解压缩就可以使用.

![图片](./img/ch00/ch0065.png)

点击文件夹中的 heidisql.exe, 在弹出对话框里点击"新建", 然后填写密码, 再点击"打开"即可连接到本机上安装的 MySQL 数据库.

![图片](./img/ch00/ch0066.png)

软件的主界面如图所示:

![图片](./img/ch00/ch0067.png)

## 2.3 [选学]使用 DBeaver 连接 MySQL

DBeaver 是一款基于 JAV 开发的**免费和开源(GPL)**的通用数据库管理工具和 SQL 客户端, 提供windows, macOS和Linux全平台支持, 能够连接包括 MySQL, PostgreSQL, Oracle, DB2, MSSQL, Sybase, Mimer, HSQLDB, Derby 等主流数据库软件在内的绝大多数兼容 JDBC 驱动的数据库. DBeaver 提供一个图形界面用来查看数据库结构、执行 SQL 查询和脚本, 浏览和导出数据, 处理 BLOB/CLOB 数据, 修改数据库结构等等.

由于是开源软件, 大家可直接从官网([https://dbeaver.io/](https://dbeaver.io/))下载, 安装完成后, 打开软件, 点击"文件"菜单下的"新建连接"图标, 并选择 MySQL:

![图片](./img/ch00/ch0068.png)

然后点击下一步:

![图片](./img/ch00/ch0069.png)

在下方弹出的设置窗口中, "服务器地址"使用默认的localhost, "数据库"暂时留空, 然后在下方填入自己设置的密码, 最后点击测试连接.

![图片](./img/ch00/ch0070.png)

本次学习主要使用一个新建的 shop 数据库, 但因为相关数据我们还没导入(建库建表及数据导入的脚本在本章第三节),因此数据库这里先留空. 等下一步导入数据后, 再进一步修改连接参数.

![图片](./img/ch00/ch0071.png)

首次连接时会提示需要下载驱动程序,

完成驱动程序的下载后, 再次点击"测试连接",如果弹出如下对话框, 则表示连接成功:

![图片](./img/ch00/ch0072.png)

点击确定并保存连接后, 以后就可以直接双击这个连接进行数据库连接了.  如果需要保存多个数据库连接, 可以使用快捷键 F2 或选中当前连接并点击鼠标右键后选择"重命名"为当前连接起一个便于识别的名称.

![图片](./img/ch00/ch0073.png)

接下来就可以开始写你的第一个 SQL 语句了: 如上图这样,选中刚刚保存的连接, 鼠标右键选第一个按钮"SQL 编辑器", 或者直接使用快捷键 F3, 就会打开一个 SQL 编辑器, 然后就可以在这里编写 SQL 语句了.

例如我们可以使用如下语句完成本教程所使用的示例数据库的创建:

![图片](./img/ch00/ch0074.png)

注意, 在使用创建数据库的语句时, 是无需在红框中选中数据库的, 但其他所有的创建表,导入数据, 和最常用的查询语句, 都需要选中相应的数据库. 在执行上述语句后, 我们可以回到连接设置里, 把默认数据库连接改为刚才创建的 shop.

![图片](./img/ch00/ch0075.png)

## 2.4 [选学]使用 Navicat 连接 MySQL

Navicat 包含了一系列的功能强大的数据库管理软件, 主要有: 完整功能版的 Navicat Premium, 以及专门用于MySQL数据库管理的 Navicat for MySQL, 用于PostgreSQL数据库管理的 Navicat forPostgreSQL, 用于SQL Server数据库管理的 Navicat for SQL Server, 用于Oracle数据库管理的 Navicat for Oracle, 等等, 但它提供的免费的版本 Navicat Lite 已足够本次课程使用, 除此之外, 上述的其他软件均为收费软件.

>注:
>Navicat 官网已经不再提供 Navicat Lite 的下载了, 但可以通过搜索引擎找到 Navicat Lite  的历史版本的下载链接. 此外, 也可以从 Navicat 官网下载 Navicat Premium 或 Navicat for MySQL 的14天试用版.
## 2.5 [选学]使用 SQLyog 连接 MySQL

SQLyog 是业界著名的 Webyog 公司出品的一款简洁高效、功能强大的图形化 MySQL 数据库管理工具. SQLyog 的企业版是收费软件, 但该软件也提供了社区版供大家使用, 虽然在功能上有些限制, 但对于本课程已经足够用了. SQLyog 社区版的下载地址为[https://github.com/webyog/sqlyog-community/wiki/Downloads](https://github.com/webyog/sqlyog-community/wiki/Downloads)


## 2.6 [选学]DataGrip的安装和连接MySQL

DataGrip是大名鼎鼎的 JetBrains 出品的数据库工具, 支持windows, macOS和Linux操作系统.


1. 创建学习用的数据库

根据《SQL基础教程》提供的MySQL版本的数据库,数据表的创建以及数据导入的代码, 经过一些修改, 创建了一份 sql 脚本, 运行该脚本可以一步到位地创建本文档所需的数据库shop及其中所有的表,并插入本教程所需要的所有数据

由于本教程聚焦于面向初学者介绍SQL查询, 对于数据库的创建, 表的创建和数据导入, 以及数据更新, 暂时不做深入介绍,有兴趣和需要的读者可参考《SQL基础教程》1-4,1-5,以及第四章.

下述SQL脚本可用于创建本教程所使用的示例数据库shop以及数据库中表的创建和数据的插入.

见《附录3 - shop.sql》

>SQL 脚本的一些要点-- v 9.08
>>0.存储引擎使用 InnoDB, 字符集改为 utf8mb4 以更好地支持中文.
>1.所有表名所使用的英文字母都改为小写(后续章节中,SQL 查询中的表名也需要相应修改为小写)
>2.所有列名所使用的英文字母确认为小写(后续章节中,SQL 查询中的列名也需要相应修改为小写)
>3.存在问题的数据, 例如 inventoryproduct 表的 inventory_id 列应为 P 开头的, 已修正为正确的数据.
>4.需测试 SQL 脚本在命令行及各个客户端中是否能被正确执行.
>* MySQL Workbench 已测试通过(在win10 使用 MySQL Workbench 8.0.21)
>* DBeaver 已测试通过(使用"执行 SQL 脚本(CTR+x)") (在win10 使用 DBeaver7.2.0)
>* HeidiSQL 已测试通过(在win10 使用HeidiSQL 11.0.0)
>* navicat 已测试通过(在win10&win7 使用 navicat premium 15.0.17)
>* sqlyog 已测试通过(在win10 使用 SQLyog 12.09)
>* 命令行 win10 下测试未通过. 插入中文数据时提示" Data too long for column 'product_name' at row 1"
# 


