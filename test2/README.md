# 图书管理系统用例建模

""""
@startuml
left to right direction
actor 图书管理员
actor 读者
rectangle  {
  图书管理员 -up--> (借出图书)
  图书管理员 -up-> (归还图书)
  图书管理员 -up-> (维护书目)
  图书管理员 -up-> (维护读者信息)
  读者 -down--> (查询书目)
  读者 -down-> (查询借阅情况)
  读者 -down-> (预定图书)
  读者 -down-> (取消预订)
}
@enduml
""""
