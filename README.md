# simpleSQL-OOP-project

Hello, world. 

这里是THU-OOP某个小组的程设大作业。
第一阶段DDL：5.5 第十周周日。冲鸭

## 系统架构
我设想中这个程序的合理结构如下：

数据表（Table） => 数据库（Database） => 前端（Front end）

功能如下：
- 数据表：数据的载体，支持题目规定的数据表层级的操作（如创建、查询、插入、更新、删除、列出等）
- 数据库：若干张数据表组成数据库。支持题目规定的数据库层级的操作（如创建、删除、列出、切换等）
- 前端：从文件中读取SQL语句，调用数据库/数据表的相关接口。

## 任务
更新一下表述
1. 设计在数据库、数据表上直接进行操作的接口，并且底层实现数据库、数据表。
 - Class Table, Database等类型的创建
 - 支持的接口有这些分类：
    * CREATE, DROP, USE 数据库的管理；SHOW 显示现有数据库
    * CREATE, DROP 数据表的管理；SHOW 显示本数据库内的所有数据表名称
    * INSERT, DELETE, UPDATE 数据表层级的数据修改命令（用到whereClause）
    * SELECT 数据表层级的查询操作（用到whereClause）；SHOW 列出数据表的属性
2. 查询语句语法分析与结果输出
 - 这一部分负责解析输入的语句，根据输入调用合适的数据库接口，并且将结果输出。这一层是沟通程序内部数据库实现与外围输入输出的桥梁。
 - 将表名、属性、值、类型、子句条件等信息传递给接口
3. 测试代码编写与测试数据构造
4. 文档维护。每一模块的文档由编写者各自完成，维护者负责统一格式，补充必要内容（包括Readme）

## 注意事项
- 遵守一定的代码规范。代码规范可以参考下https://blog.csdn.net/p942005405/article/details/80282572
- 完成自己负责部分的文档编写。具体编写内容可以包括这段代码实现功能、架构分析（可以配图）、接口用法（函数功能、参数解释、返回值，有些时候可以添加示例代码）等。其实，一些关键函数的接口用法应当写在代码注释中，养成勤写注释的习惯，会方便写文档。（这些都是我刚刚随便想的）建议用Markdown编写。
- 编写的程序模块较多，应当对自己的程序模块进行充分测试。一种重要手段叫做单元测试。单元测试就是在开发阶段对于每个单元（通常是一个函数、一个类等等）专门设计数据、编写测试代码、运行结果，检查结果是否符合期待。尽量保证自己编写的每一行代码、每一种情况都被考虑到（保证代码覆盖率）。
- 在编写代码的过程中，各人负责的部分有一定的耦合，A可能需要调用B编写的代码。在负责各自的部分时，先把对外部的接口规定好（其实对于C++程序，接口都在头文件里），方便其他人调用，编写完接口后再编写实现，这样就可以一定程度上实现并行编程了
- 学习一下MySQL的知识~