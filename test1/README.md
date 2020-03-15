实验1
> @startuml
|教务处|
start
:安排考试;
:考试安排表/
|教师|
:出卷;
fork
   :A,B试卷/
fork again
   :打印审批表/
    |系主任|
   :审批签字;
   :打印审批表/
end fork
|教务处|
:打印试卷;
:试卷/
|学生|
:参加考试;
:答卷/
|教师|
:阅览出成绩;
fork
   :答卷/
   :装订存档;
fork again
   |教务处|
   :成绩单;
   if(有不及格?) then(有)
   :安排补考;
   endif
   fork
   :补考安排表/
   detach
   fork again
   end fork
end fork
|教师|
:期末考试流程结束;
stop
@enduml
