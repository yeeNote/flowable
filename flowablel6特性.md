## 一、flowablel历史：

flowable第一稳定版本是5.22基于avtiviti5.21研发的，最新版本是6.4.0，融合了avtiviti6并修复了avtiviti6的bug.

## 二、flowablel6特性

- 对CMMN 1.1引擎的大量增加，包括定时器支持、repetition 支持、DMN和HTTP任务支持以及变量查询支持。
- Rest风格接口接口集成了Swagger。目的是为了同步所有可以用的接口。以防止书写接口文档方式容易造成接口文档的不同步以及遗漏。
- 引入了ChangeActivityStateBuilder：该类可以实现在同一个流程定义文档中实现任意节点的跳转。
- 增强了CMMN  Modeler 设计器调色板。涉及到的内容有：定时器事件监听器、DMN和HTTP任务、添加了额外的属性，比如定时器表达式和重复表达式。

- Flowable Task app中支持CMMN引擎。

### 2.1 flowable6.2.1新特性

- 引入了一个全新的CMMN引擎，该引擎的版本为1.1

  ​     这提供了CMMN 1.1 OMG标准的实现（[关于cmmn可以访问官网](http://www.omg.org/spec/CMMN/1.1/) ）。这个新引擎已经投入了很多精力在开发以及完善。它使用一组为CMMN引擎执行优化的数据库表。我们添加了一个新的CMMN用户指南来帮助您入门。请注意，因为这是第一个版本，CMMN引擎被标记为一个实验特性，缺少像计时器和HTTP和决策任务等功能将在下一个版本中添加。

- 在Flowable  Modeler应用程序中添加了一个CMMN编辑器。

- 增加了对Flowable  task 应用程序的CMMN案例支持。

- BPMN和CMMN引擎共享许多公共服务，如任务、变量、身份链接和作业。

  ​     从核心BPMN引擎模块提取这些服务，并为每一个服务创建新的模块。BPMN和CMMN引擎利用这些服务来提供示例任务和变量的支持。这种方法在部署模型中是非常灵活的。

### 2.2 flowable6.3.1新特性

- 引入一个app引擎，当启动Flowable 任务应用程序时，所有应用程序部署都会自动迁移到新的app引擎。
- 向CMMN引擎添加了异步历史支持。
- 将更多的历史信息添加到具有历史计划主题的CMMN引擎中。
- 改进了Spring引导支持，并升级到Spring Boot 2.0.2。
- 在Flowable任务应用程序中增强的调试器来计算表达式和脚本。
- 使作业服务更通用于范围类型属性，以提高针对不同作业类型运行不同作业处理程序的可能性



### 2.3 Flowable最新版（6.4） 新特性

- 使用Spring为所有集成模块升级到Spring 5.x。目前spring版本是5.0.8。
- JPA使用的版本是2.1.
- JMS版本是2.x.
- 删除org.springframework.security.authentication.encoding.PasswordEncoder类构造函数。
- 支持中文。
- 修复节点名称不显示bug.
- 修复连线不显示bug。
- 增加执行树日志。
- 增加一系列的操作手册。
- 完善CMMN引擎。
- 增加mongdb支持（可以替代关系型数据库）。
- 增加引用流程completeAsync特性（异步完成）。
- modler设计器中脚本任务增加scriptautostorevariables属性。
- rest模块支持json数据格式。
- ensureRootProcessInstanceInitialized bug修复
- ContentEngine引擎支持。
- 支持使用Java.Time.Times变量和定时器持续时间表达式



## 三、flowable里程碑

### 6.4.0（最近发布）

- 流程实例迁移的第一个版本

- JUnit 5和Jupiter重构

- 在MongoDB上运行Flowable的概念证明


### 6.4.1（11月底/ 12月初）

- 流程实例迁移的第二版，涵盖更高级的用例
- CMMN引擎改进了覆盖范围和其他新功能
- 在DMN引擎中添加对DMN 1.2 XML文件的支持
- 添加了对处理默认租户和租户特定流程/案例/决策定义的更多支持

### 6.5.0（tbd）

- DMN DRD
- 流程实例迁移的增强版本
- 对消息队列的开箱即用支持（包括相关性）
- Heatmaps显示最常采用的过程路径
- MongoDB BPMN引擎的稳定版本
- Kubernetes支持


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5NDYwNzczMV19
-->