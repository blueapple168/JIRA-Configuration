# JIRA 自定义流程配置手册  
最近折腾了一下JIRA，怕忘记，就当写给自己留作备份  

&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;    
&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;蝶恋花&nbsp;·&nbsp;卷絮风头寒欲尽  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;赵令畤   
卷絮风头寒欲尽。坠粉飘红，日日香成阵。新酒又添残酒困。今春不减前春恨。  
蝶去莺飞无处问。隔水高楼，望断双鱼信。恼乱层波横一寸。斜阳只与黄昏近。  
&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;  
&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;&gt;

装逼完毕，切入正题  
----  
# 目录
- [写在前面](#写在前面)
- [基本模块](#basic)
  - [项目管理](#projectManagement)
  - [全局权限](#globalPermission)
  - [全局角色](#globalRoles)
  - [用户管理](#usersManagement)
- [问题类型](#issueType)
  - [项目使用问题类型](issuneTypeConnect)
- [工作流](#workFlow)
  - [自定义工作流状态](#workFlowStatus)
  - [自定义工作流](#customWorkFlow)
  - [项目使用工作流](#workFlowConnect)
- [操作界面](#operationInterface)
  - [自定义字段](#customField)
  - [自定义界面](#customInterface)
  - [关联项目](#operationInterfaceConnect)
  - [工作流子界面使用](#childInterface)
- [字段配置](#fieldConfiguration)
  - [维护配置](#fieldConfigurationSetting)
  - [关联项目](#fieldConfigurationConnect)
- [权限](#customPermission)
  - [自定义权限方案](#permissionPlan)
  - [项目使用权限方案](#permissionPlanConnect)
  - [关于工作流中权限限制](#workFlowPermission)
- [邮件提醒](#email)
  - [配置邮件](#emailSetting)
  - [配置通知方案](#notificationPlan)
  - [项目使用通知方案](#notificationPlanConnect)
  - [工作流中动作使用自定义通知](#workFlowNotification)
- [其他设置](#othersSetting)
  - [附件](#attachment)
  - [经办人](#agent)
  - [系统面板](#dashbord)
  - [过滤器](#filter)
  - [邮件定时发送](#emailTiming)
  - [列表字段调整](#filedSetting)
  - [邮件模板注意事项](#emailTemplate)
  - [批量操作](#batchOperation)
  
  
***
## 写在前面
此文档基于自定义一个事件流程对JIRA中基本功能进行介绍  
旨在让阅读人员大体了解JIRA是如何配置并投入使用
***
## <span id="basic">基本模块</span>  
### <span id="projectManagement">项目管理</span>  
### <span id="globalPermission">全局权限</span>  
### <span id="globalRoles">全局角色</span>  
### <span id="usersManagement">用户管理</span>  
***
## <span id="issueType">问题类型</span>  
### <span id="issuneTypeConnect">项目使用问题类型</span>  
## <span id="workFlow">工作流</span>  
### <span id="workFlowStatus">自定义工作流</span>  
### <span id="customWorkFlow">自定义工作流状态</span>  
### <span id="workFlowConnect">项目使用工作流</span>  
***
## <span id="operationInterface">操作界面</span>  
### <span id="customField">自定义字段</span>  
### <span id="customInterface">自定义界面</span>  
### <span id="operationInterfaceConnect">项目使用界面</span>  
### <span id="childInterface">工作流子界面使用</span>  
***
## <span id="fieldConfiguration">字段配置</span>  
### <span id="fieldConfigurationSetting">维护配置</span>  
### <span id="fieldConfigurationConnect">关联项目</span>  
***
## <span id="customPermission">权限</span>  
### <span id="permissionPlan">自定义权限方案</span>  
### <span id="permissionPlanConnect">项目使用权限方案</span>  
### <span id="workFlowPermission">工作流中权限控制</span>  
***
## <span id="email">邮件提醒</span>  
### <span id="emailSetting">配置邮件</span>  
### <span id="notificationPlan">配置通知方案</span>  
### <span id="notificationPlanConnect">项目使用通知方案</span>  
### <span id="workFlowNotification">工作流中动作使用自定义通知</span>  
***
## <span id="othersSetting">其他设置</span>  
### <span id="attachment">附件</span>  
### <span id="agent">经办人</span>  
### <span id="dashbord">系统面板</span>  
### <span id="filter">过滤器</span>  
### <span id="emailTiming">邮件定时发送</span>  
### <span id="filedSetting">列表字段调整</span>  
### <span id="emailTemplate">邮件模板注意事项</span>
### <span id="batchOperation">批量操作</span>
  
