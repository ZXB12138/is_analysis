# 实验4：图书管理系统顺序图绘制
|学号|班级|姓名|照片|
|:-------:|:-------------: | :----------:|:---:|
|201710414231|软件(本)17-2|周旭波|![me](../me.jpg)|
## 图书管理系统的顺序图

## 1. 借书用例

## 1.1. 借书用例PlantUML源码
```
@startuml
actor Reader
actor Admain

Reader -> Admain:借书
Admain -> Records借阅记录类:check()
Records借阅记录类 -> book书类:borrow()
book书类 --> Records借阅记录类:记录信息
Records借阅记录类 --> Admain:借阅成功
Admain --> Reader:给书
@enduml
```
## 1.2. 借书用例顺序图
![a](a.png)

## 1.3. 借书用例顺序图说明

读者将借书请求发给管理员，管理员收到后先从Records类中检查借阅记录，确认无误后从book类中获取要借的书的信息并将借阅信息添加到Records类中，返回借阅成功，管理员在把书给读者，借书结束




## 2. 还书用例

## 2.1. 还书用例PlantUML源码
```
@startuml
actor Reader
actor Admain

Reader -> Admain:还书
Admain -> Records借阅记录类:check()
Records借阅记录类 -> book书类:return()
book书类 -> Records借阅记录类:改变借阅状态
book书类 -> Records借阅记录类:计算是否逾期
Records借阅记录类 --> Admain:return()
Admain --> Reader:缴纳罚款
Admain --> Reader:还书成功
@enduml
```
## 2.2. 还书用例顺序图

![b](b.png)

## 2.3. 还书用例顺序图说明

读者还书，管理员先对Records类中进行借阅信息登记，确认无误后将Records类中的借阅状态改变，并计算是否逾期将信息返回给Records类，管理员再通过返回的信息判断是否需缴纳罚金，还书结束
