## 1 创建数据库
```sql
create database stu
```
## 2 建立学院表
```sql

CREATE TABLE school
 (Sname CHAR(20)  NOT NULL,
  Sdept INT PRIMARY KEY,
  Sdname CHAR(20) UNIQUE NOT NULL
  )character set=utf8;
  
 use stu;
 CREATE TABLE information
  (Ino CHAR(20) PRIMARY KEY,
   Iname CHAR(20) NOT NULL,
   Isex CHAR(8) CHECK (sex in ('男' ,'女')),
   Iage SMALLINT NOT NULL,
   Iphone INT(11) UNIQUE NOT NULL,
   Sdept INT,
   FOREIGN KEY (Sdept) REFERENCES school(Sdept)
 )character set=utf8;
 
 CREATE TABLE score
  (Ino CHAR(20) NOT NULL,
   Cno CHAR(20) NOT NULL,
   grade SMALLINT check(grade>=0 and grade<=100),
   PRIMARY KEY (Ino,Cno),
   FOREIGN KEY (Ino) REFERENCES information(Ino),
   FOREIGN KEY (Cno) REFERENCES course(Cno)
   )character set=utf8;
   
   CREATE TABLE course
  (Cno CHAR(4) PRIMARY KEY,
   Cname CHAR(20) UNIQUE NOT NULL,
   Ccredit SMALLINT  check(Ccredit>=0  and Ccredit<=10)
   )character set=utf8;

alter table score 
add statu int default 0 check (statu in(1,0));
```
# MySQL 关系型数据库
### MySQL特点   
   
   * MySQL是开源的，所以你不需要支付额外的费用。
   * MySQL支持大型的数据库。可以处理拥有上千万条记录的大型数据库。
   * MySQL使用标准的SQL数据语言形式。
   * MySQL可以允许于多个系统上，并且支持多种语言。这些编程语言包括C、C++、Python、Java、Perl、PHP、Eiffel、Ruby和Tcl等。
   * MySQL支持大型数据库，支持5000万条记录的数据仓库，32位系统表文件最大可支持4GB，64位系统支持最大的表文件为8TB。
   * MySQL是可以定制的，采用了GPL协议，你可以修改源码来开发自己的MySQL系统。
   


### MySQL安装

  1. 更新源
   * sudo vim /etc/apt/sources.list

       2.  将下面的源粘贴到源列表
  
  * deb http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse
* deb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse
* deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse
* deb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse
#### 测试版源
* deb http://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse
#### 源码
* deb-src http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse
* deb-src http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse
* deb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse
* deb-src http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse
##测试版源
* deb-src http://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse
##### Canonical 合作伙伴和附加
* deb http://archive.canonical.com/ubuntu/ xenial partner
* deb http://extras.ubuntu.com/ubuntu/ xenial main

3. 进行更新
* sudo apt-get update 
4. 安装Apache以及MySQL
* sudo apt-get install tasksel
* sudo tasksel
5. 安装workbench
* sudo apt-get install mysql-workbench

### MySQL命令
#### 连接Mysql 格式： mysql -h 主机地址 -u用户名 －p用户密码
#### 连接到本机上的MYSQL
* 如：mysql -u root -p 回车后提示你输密码.注意用户名前可以有空格也可以没有空格，
但是密码前必须没有空格，否则让你重新输入密码。如果刚安装好MYSQL，超级用户root是没有密码的，
故直接回车即可进入到MYSQL中了，MYSQL的提示符是： mysql>
#### 连接到远程主机上的MYSQL
* 假设远程主机的IP为：110.110.110.110，用户名为root,密码为abcd123。则键入以下命令： mysql -h110.110.110.110 -u root -p 123;（注:u与root之间可以不用加空格，其它也一样）
#### 退出MYSQL命令
* quit
* exit
#### 修改密码
* 格式：mysqladmin -u用户名 -p旧密码 password 新密码
