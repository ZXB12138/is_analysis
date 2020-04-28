# 实验5：图书管理系统数据库设计与界面设计

## 1.数据库表设计
## 1.1读者/用户表
| 字段 | 类型 | 主键,外键 | 可以为空 | 默认值 | 约束 | 说明 |
| ------| ------ | ------ | ------  | ------ | ------ | ------ | 
| id | varchar(9) | 主键 | 否 | | | 用户编号 | 
| name | varchar(4) |  | 否 | | | 用户姓名 | 
| sex | varchar(2) |  | 否 | | | 用户性别 | 
| username | varchar(20) |  | 否 | | | 用户学号\账号 | 
| password | varchar(20) |  | 否 | | | 用户密码 | 

## 1.2书籍表
| 字段 | 类型 | 主键,外键 | 可以为空 | 默认值 | 约束 | 说明 |
| ------| ------ | ------ | ------  | ------ | ------ | ------ | 
| id | varchar(9) | 主键 | 否 | | | 书籍编号 | 
| name | varchar(20) |  | 否 | | | 书名 | 
| author | varchar(10) |  | 否 | | | 作者 | 
| num | int(10) |  | 否 | | | 书籍数量 | 
| publisher | varchar(20) |  | 是 | | | 出版社 | 
| type | varchar(10) |  | 是 | | | 书籍类别 | 

## 1.3借阅记录表
| 字段 | 类型 | 主键,外键 | 可以为空 | 默认值 | 约束 | 说明 |
| ------| ------ | ------ | ------  | ------ | ------ | ------ | 
| id | varchar(9) | 主键 | 否 | | | 借阅记录编号 | 
| userid | varchar(9) | 外键 | 否 | | | 借阅者编号 | 
| bookid | varchar(9) | 外键 | 否 | | | 借阅书籍编号 | 
| bookname | varchar(20) | 外键 | 否 | | | 借阅书名 | 
| borrowDate | datetime |  | 否 | | | 借阅日期 | 
| returnDate | datetime |  | 是 | | | 还书日期 | 
| time | varchar(10) |  | 否 | | | 借阅时间 | 

## 1.3管理员表
| 字段 | 类型 | 主键,外键 | 可以为空 | 默认值 | 约束 | 说明 |
| ------| ------ | ------ | ------  | ------ | ------ | ------ | 
| id | varchar(9) | 主键 | 否 | | | 管理员编号 | 
| name | varchar(4) |  | 否 | | | 管理员姓名 | 
| username | varchar(20) |  | 否 | | | 管理员账号 |
| password | varchar(20) |  | 否 | | | 管理员密码 | 

# 2. 界面设计
## 2.1. 读者登陆界面设计
![a.jpg](读者登录界面)
[读者登录界面](https://zxb12138.github.io/is_analysis/test5/html/page_1.html).
* 用例图参见：登陆用例
* 类图参见：管理员类，读者/用户类
* 顺序图参见：login()
* API接口如下：

1.登陆

* 功能：登陆用户
* 请求地址： http://bookSystem/v1/api/login
* 请求方法：Post
* 请求参数：

|参数名称|	必填|	说明|
| ------| ------ | ------ | 
|access_token|	是|	用于验证请求合法性的认证信息|
|method|	是|	固定为 “Post”|

* 返回实例：

```
{
    "user": "username，password",
    "code": 200
}
```
* 返回参数说明：

|参数名称|	说明|
| ------| ------ |
|username	|用户名\学号|
|code	|状态码|

## 2.2. 系统主界面设计
![b.jpg](系统主界面)
[系统主界面](https://zxb12138.github.io/is_analysis/test5/html/page_2.html).

## 2.3. 书籍界面设计
![c.jpg](书籍界面设计)
[书籍界面](https://zxb12138.github.io/is_analysis/test5/html/page_3.html).
## 2.4. 借阅记录界面设计
![d.jpg](借阅记录界面设计)
[借阅记录界面](https://zxb12138.github.io/is_analysis/test5/html/page_4.html).
