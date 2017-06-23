## 学生信息管理系统的创建 

 1.在linux环境下安装mysql，并运行；
 
 2.在linux环境下安装mysql-workbench，并运行；
 
 3.在mysql-workbench下创建stu数据库，在其下面创建四个表：
 
       information  
       
       school 
       
       course 
       
       score
       
  4.在linux下，让其与mysql和mysql-workbench相连接；
  
  5.最后进行修改，美化，完善其功能。
  
## 学生管理系统表的建立

### schllol表
   
字段名称 | 释义 | 属性 | 备注  
--------|-----|------|-----   
Sname | 学校名称 | char(20) | 唯一且不唯空 
Sdept | 院编号 | char(5) | 主键 
Sdname | 系名 | char(20) | 主健且不为空 

### course 表

字段名称 | 释义 | 属性 | 备注  
--------|-----|------|-----  
Cno | 课程号 | char(4) | 主键
Cname | 课程名 | (20) | 唯一但不为空 
Credit | 学分 | smallint | 0到10之间的数
Cpno | 先修课| char | 主键 

### information 表

字段名称 | 释义 | 属性 | 备注  
--------|-----|------|-----  
Ino | 学号 | char(20) | 主键 
Iname | 姓名 | char(20) | 主键但不为空 
Isex | 性别 | char(2) | 男或女 
Iage | 年龄 | smallint | 不为空 
Iphone | 联系电话 | char | 唯一且不为空 
Idept | 院编号 | char(5) | 主键

### score 表

字段名称 | 释义 | 属性 | 备注  
--------|-----|------|-----  
Ino | 学号 | char(20) | 主键之一
Cno | 课程号 | char(20) | 主键之一
grade | 成绩 | smallint | 0到100的数









































