# mysql——cmd进入mysql及常用的mysql操作

#### **cmd进入mysql操作**

win+R，输入cmd，[打开cmd](https://so.csdn.net/so/search?q=打开cmd&spm=1001.2101.3001.7020)窗口，进入到 mysql bin目录的路径下

第一步：[启动mysql](https://so.csdn.net/so/search?q=启动mysql&spm=1001.2101.3001.7020)服务，可以通过“net start myql”命令实现；

第二步：先使用[DOS命令](https://so.csdn.net/so/search?q=DOS命令&spm=1001.2101.3001.7020)进入mysql的安装目录下的bin目录中；

第三步：在命令行输入：mysql -u 用户名 -p密码；回车；

```
mysql -u root -p
```

- 输入命令 `mysql -u root -p` 回车
- 输入密码
- 输入`use temp_database ;`
- 输入查询语句

cmd下的mysql操作
数据库有关操作

1.查询时间：select now();

2.查询当前用户：select user();

3.查询数据库版本：select version();

4.列出数据库：show databases;

5.选择数据库：use databaseName;

6.建立数据库：create database databaseName;

7.查看新创建的数据库信息：show create database databaseName;

8.删除数据库：drop database databaseName;

数据表有关操作

1.查看数据表存储引擎：

```
show engines；
```

2.列出表格：

```
show tables；
```

3.创建表：

```
CREATE TABLE tableName(
    c_num int (11) not null  unique primary key auto_increment,
    c_name varchar (50),
    c_contact varchar (50),
    c_city varchar (50),
    c_birth datetime not null
);
```

4.查看表结构：

```
desc tableName;
```

5.显示表格列的属性：

```
show columns from tableName;
```

6.修改字段类型：

```
alter table tableName modify fieldName newFieldType; 
```

7.字段改名：

```
alter table tableName change oldFieldName newFieldName newFieldType; 
```

8.表改名：

```
alter table oldTableName rename newTableName;
```

9.复制表：

```
create table tableName2 select * from ttableName1;
```

10.插入表中一行记录：

```
insert into tableName values ("value1","value2","value3"......);
```

11.删除表中一行记录：

```
delete from tableName where columnName=value; //不加where将删除全部数据
```

12.更新表中一行记录：

```
update tableName set columnName=value where columnName=value; 
```

13.查询表中所有记录：

```
select * from tableName;
```

14.删除表：
```
drop TABLE tableName;
```

**mysql退出**：

```
exit;
quit;
\q;
```

在dos下运行net start mysql 不能启动mysql！提示**发生系统错误 5；拒绝访问！**切换到管理员模式就可以启动了。所以要以管理员身份来运行cmd程序来启动mysql。

**dos命令的基本操作：**

盘符: 例如想进入D盘  d:  

cd    进入到当前盘某个目录。
cd \   进入当前盘根目录
cd \windows  进入到当前盘Windows目录
cd..   退出到上一级目录

注：  进入含有特殊字符目录时需要加引号  例如 cd "c:\program files"

在cmd中，不需要你全输入，你只需要按p键，然后按tab键，就可以定位，以p字母开头的文件/文件夹名。多次按tab键可切换文件/文件名