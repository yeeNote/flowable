

## 一、flowable和业务对接



### 1.1 业务对接流程

​	根据现有业务需要，定义各个业务流程类别，不同的类别对于不同的流程。启动对应的流程实例。



### 1.2 审批操作流程的对接

​	由于审批操作类型有：**会签、或签、依次审批**等，可以采用配置人工任务中的**多实例中的串行和并行规则**，来指定是审批的候选人是否需要全部审批通过才能进入下一流程，还是某个领导一票否决，亦或是设置每个审批候选人的权重(现有的floable6.4版本不支持，需要自行扩展)，根据权重阈值来决定是否需要进入下一流程。

## 1.3 用户中心的对接

  在flowable中，权限主要是控制各个模块的访问控制，登录控制。在实际的流程中没有控制。flowable中只有用户，组，权限的概念。

flowable官网上提供了三种方案：

- 方案1：

  同步业务用户数据到flowable相关表中，flowable-idm模块也提供了相关Restful接口。

- 方案2：

  扩展代码，自己实现userEntitiMananger。

- 方案3：

  用视图取代原来的表，这种方案不会破坏动业务数据结构和flowable中用户数据结构。



​	根据现有用户中心的用户角色，可以把角色下面的所有人员对于flowable引擎中的组，该角色下的人员即为flowable中此组下面的人员。



### 1.4 表单的对接

​	流程引擎中表单的数据，是可以经过上一节点传递到下一节点。定义表单流程时，每个流程节点均可以设置表单的字段的可见性、可读、可写等属性，在不同流程节点的表单中字段是否可以看到、编辑等等。

​	动态表单对接：定义流程引擎时，如果定了动态表单，并且已经发布了相关流程，可以通过流程相关接口获取到表单信息，以流或者html文件等等信息，返回给前端，可以实现动态渲染。在流程的各个节点可以通过流程引擎变量获取各个节点表单的内容。

​	外置表单：定义流程时通过form.key关联到外部表单，但是发布流程时，外置的表单需要和流程引擎一起发布。在流程的各个节点可以通过流程引擎变量获取各个节点表单的内容。

### 1.5 租户对接

​	flowable中的租户是用来区分不同业务系统的，而且租户在流程中是可以继承的。这个概念和用户中心的租户是一致的。可以直接对接。
<!--stackedit_data:
eyJoaXN0b3J5IjpbODcyMTUxODE4XX0=
-->