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
- [基本模块](#基本模块)
  - [用户管理](#用户管理)
  - [项目管理](#项目管理)
  - [全局权限](#全局权限)
  - [全局角色](#全局角色)
- [问题类型](#问题类型)
  - [项目使用问题类型](项目使用问题类型)
- [工作流](#工作流)
  - [自定义工作流状态](#自定义工作流状态)
  - [自定义工作流](#自定义工作流)
  - [项目使用工作流](#项目使用工作流)
  - [工作流执行更新字段](#工作流执行更新字段)
- [操作界面](#操作界面)
  - [自定义字段](#自定义字段)
  - [自定义界面](#自定义界面)
  - [关联项目](#关联项目)
  - [工作流子界面使用](#工作流子界面使用)
- [字段配置](#字段配置)
  - [维护配置](#维护配置)
  - [关联项目](#关联项目)
- [权限](#权限)
  - [自定义权限方案](#自定义权限方案)
  - [项目使用权限方案](#项目使用权限方案)
  - [关于工作流中权限限制](#关于工作流中权限限制)
- [邮件提醒](#邮件提醒)
  - [配置邮件](#配置邮件)
  - [配置通知方案](#配置通知方案)
  - [项目使用通知方案](#项目使用通知方案)
  - [工作流中动作使用自定义通知](#工作流中动作使用自定义通知)
- [其他设置](#其他设置)
  - [附件](#附件)
  - [经办人](#经办人)
  - [系统面板](#系统面板)
  - [过滤器](#过滤器)
  - [邮件定时发送系统事件](#邮件定时发送系统事件)
  - [列表字段调整](#列表字段调整)
  - [邮件模板注意事项](#邮件模板注意事项)
  - [批量操作](#批量操作)
  - [解决结果](#解决结果)
  - [修改日期显示](#修改日期显示)
  
***
##  写在前面  
此文档基于自定义一个事件流程对JIRA中基本功能进行介绍，旨在让阅读人员大体了解JIRA是如何配置并投入使用。  
JIRA具体作用不在此文档中赘述，此文档主要讲述如何进行自定义配置。  
建议首次配置人员阅读全文后进行再进行配置，以免没有完整的知识体系。  

此文档风格是，先说菜单，然后说明其作用。  

配置环境：  
JIRA版本 6.3.3  、汉化、管理员用户。  
不使用管理员用户没有设置菜单。
***
##  基本模块  

###  用户管理  
设置-用户管理  
任何一个系统，首要的功能就是能进行访问，此处涉及到用户概念。  
用户管理提供维护用户、用户组功能 。   
新建的用户都属于jirauser用户组，此组拥有基本的权限，详见[全局权限](#全局权限)介绍。  
JIRA系统提供用户自行注册的功能，此开关在“设置-系统-设置-方式”中维护。  
###  项目管理 
设置-项目   
JIRA中是按照项目的维度进行配置管理，任何配置必须关联在项目下才能在当前项目生效；关于项目的概念在此引入是比较唐突，但是下面的讲述需要用到。
###  全局权限  
设置-系统-全局权限  
JIRA中权限分为全局权限和自定义（私有）权限；  
全局权限中配置后则对系统内所有用户生效（例如登录等）；JIRA中全局权限只能通过“用户组”进行分配。 
私有权限不在此讲述，详见[权限](#权限)。
###  角色  
设置-系统-角色  
JIRA中定义的角色，是全局的角色，一经定义，全部项目中都包含有此角色 。  
如果需要为项目分配私有角色成员：设置-项目-进入项目-管理-ROLES。  
注意：项目中的ROLES维护的成员，是基于项目私有的。如果需要设置全局的角色成员，在“设置-系统-角色”中定义。
***
截止到目前，基本对JIRA基础模块有了认知，接下来进入自定义配置流程说明。
***
##  问题类型  

设置-问题-问题类型。  
问题类型是JIRA比较重要的概念，JIRA中很多地方都有此涉及到问题类型；  
简单的来说，问题类型的存在可以使JIRA更加灵活的进行配置。  
例如：  
我们可以针对不同的问题类型，设置不同的工作流、操作界面等；如果没有问题类型的概念，则一个项目只能使用单一的配置。
###  问题类型方案  
设置-问题-问题类型方案  
问题类型方案相当于维护了问题类型的集合，有两个作用：  
1.可以对问题类型进行分组。  
2.是问题类型和项目关联的桥梁，项目能使用哪些问题类型，在此关联。
###  项目使用问题类型  
项目-管理-问题类型  
此处可以设置项目具体可以使用的问题类型，但是需要注意的是项目只能通过“问题类型方案”才能关联到具体的问题类型    
##  工作流  
设置-问题-工作流  
工作流是JIRA中最为重要的模块之一，任何时间的流转，都需要涉及到工作流。  
JIRA中有默认的预定义工作流，但我们这里主要讲述自定义工作流  
###  自定义工作流状态  
设置-问题-问题属性-状态  
工作流首先需要涉及到的是工作流中的状态，新建工作流之前必须维护其涉及到的状态，在此处维护  
###  自定义工作流
设置-问题-工作流-工作流  
此处可以维护JIRA中的工作流，已生效的工作流说明已经被项目使用，未生效的则没有。  
维护步骤：  
1.点击右上角“新增工作流”进行新增 。  
2.在新增/编辑界面中“add status”即可使用上面自定义的工作流状态。   
3.维护完工作流之后需要“发布”才能生效。    
如果在新建工作流动作时报错（错误信息忘记记下了..)，可以尝试将工作流与项目解绑之后再进行操作 。 
### 工作流方案  
设置-问题-工作流方案  
如果需要不同的问题类型使用不同的工作流，则可以在此处进行维护。  
虽然项目可以直接和工作流产生关联进行使用，但是JIRA中为我们提供了更加灵活的配置方式， 
在工作流方案中，我们可以配置不同的“问题类型”使用不同的工作流来流转，所以在具体使用过程中，建议通过工作流方案来和项目产生关联。
###  项目使用工作流  
项目-管理-工作流  
工作流配置完毕，需要使用到具体项目中，
这里可以维护项目使用的具体工作流，不建议直接选择工作流，而是建议选择“工作流方案” ，原因见上面讲述的[工作流方案](#工作流方案)的作用。

### 工作流执行更新字段
见：[工作流执行修改解决结果](#工作流执行修改解决结果)，貌似只能修改系统预定义字段。  
***
##  操作界面  

JIRA为我们预定义了操作界面（例如问题的创建、编辑、修改），但是不一定适合我们实际使用；在实际使用的过程中，我们可能需要自定义界面、自定义字段进行使用。  
###  自定义字段  
设置-问题-自定义字段  
定义一个界面，首先需要考虑的是字段信息的展示；JIRA中的操作界面是通过选择字段组成的一个完整的界面。    
JIRA中提供了丰富的预定义字段，可以直接使用；如果涉及到需要自定义字段，则在此界面进行维护。  
自定义字段界面可以维护字段、备注、备选值、默认值等信息  
###  自定义界面  
设置-问题-界面  
此处可以自定义操作界面，不同的操作动作可以定义不同的界面。    
维护完成界面后，不可以直接被项目使用，需要先和[界面方案](#界面方案)产生关联。
###  界面方案
设置-问题-界面方案  
界面方案可以定义不同的操作（创建、查看、编辑）使用不同的界面。   
界面方案不可以直接被项目使用，需要和[问题类型界面方案](#问题类型界面方案)产生关联。
### 问题类型界面方案
设置-问题-问题类型界面方案  
在前面[问题类型](#问题类型)中讲述到，问题类型可以使JIRA配置更加灵活；在问题类型界面方案中，可以使不同的问题类型使用不同的界面方案；这样一来，某个项目中不同的问题类型下，不同的操作就可以使用不同的界面，是不是很灵活。  
配置完毕后，接下来看如何使用到具体项目中。
### 项目使用自定义界面  
项目-管理-界面  
自定义界面被项目使用，必须通过如下关联：  
1.配置界面。  
2.配置界面方案，关联界面。  
3.配置问题类型界面方案，关联界面方案。  
4.项目与问题类型界面方案关联。  
在此处配置完毕后，即可使用。  
###  工作流子界面使用  
在实际使用过程中，可能有如下需求：  
用户不想每次都选择编辑来修改数据，而是在在执行工作流过程中，当点击某个按钮（执行动作）时，能否弹出一个界面。  
答案是肯定的。  
设置方式：  
1.在“设置-问题-界面”中，建立需要操作的界面。  
2.进入工作流，进入编辑模式，选中执行动作，点击右上角“编辑”按钮，在弹出框中的“界面”中选择第一步配置的界面。  
***
##  字段配置  
字段配置的大体作用是：  
控制某些字段在录入的时候是否必选  
有默认值的字段如果不在操作界面使用，是否在录入后显示值等  
###  维护配置  
设置-问题-字段配置   
其他的没什么好说的，这里需要说明一点：  
如果字段A设置了默认值，但是没有在操作界面中使用，则录入后在列表中查看也是有数据的；如果需要使其数据为空，则需要设置字段属性为“隐藏”。  
此处维护的配置不能直接使用到项目上，需要与[字段配置方案](#字段配置方案)关联后才能使用。
### 字段配置方案
设置-问题-字段配置方案  
维护不同的问题类型使用不同的字段配置方案。  
###  关联项目  
项目-管理-字段  
关联上面设置的字段配置，关联后才能生效。

***
##  权限  
权限控制可以针对不同的用户、用户组、角色甚至自定义字段进行权限管控。 
###  自定义权限方案  
设置-问题-权限方案  
配置操作权限，如果设置后[关联项目](#项目使用权限方案)不生效，需要注意是否和[全局权限](#全局权限)存在冲突。 
###  项目使用权限方案
项目-管理-权限  
配置项目使用的权限方案。
###  工作流中权限控制
在执行工作流过程中，希望某个动作能被权限控制，这个是可以实现的，但是不在权限方案中配置。   
配置步骤：  
1.进入工作流，进入编辑模式。  
2.选中执行动作，选择右边的“触发条件”，进行设置。  
此处需要注意的是，在“触发条件“中选择”并“和”或“的关系，否则多个条件使用时容易造成逻辑错误。   
***
##  邮件提醒   
当系统中有创建、编辑、工作流执行等操作，都可以设置相应的提醒。  
JIRA中使用邮件形式进行消息提醒。 
###  配置邮件  
设置-系统-邮件-outgoing mail  
发送邮件的第一步，需要配置邮件服务器  
配置完毕后，发送测试邮件，一般jira的邮件延迟会在5分钟之内，能收到则说明邮件配置成功 。
###  配置通知方案  
设置-问题-通知方案  
通知方案可以设置具体在项目中执行了什么操作会发送邮件。  
###  项目使用通知方案  
项目-管理-通知设置  
将[通知方案](#配置通知方案)和项目关联；
通知方案和项目关联后，项目执行对应操作，则会根据通知方案中的配置进行邮件提醒
###  工作流中动作使用自定义通知  
在具体事项流转的过程中，我们需要在工作流某一动作执行后，发送邮件给相应的人员，JIRA是支持我们自定义的，步骤如下：  
1.设置-系统-事件；在这里定义一个事件，这个事件是为了我们在工作流执行后触发的。事件的定义是全局的，细心的同学可能也发现了，事件列表中定义的事件，和“通知方案”中的事件是一致的。  
（在定义事件时需要注意：新增事件时模板的选择，决定了邮件通知的模板，建议优先考虑issue updated,这样发送的邮件中我们可以看到前后值的变化）  
2.正如第一步所说，在系统事件中定义了事件，就可以在通知方案中设置具体需要被通知的对象，这一步和上面讲述的[配置通知方案](#配置通知方案)操作和作用都是一致的。  
3.将工作流和事件绑定，进入“系统-问题-工作流”，进入编辑模式，选中动作，选择右边“结果处理”，将“监听器会在进程结束后触发 一般事件 事件。”改为自定义事件，发布工作流，完成。  
***
***
截止上面步骤，一套完整的自定义流程搭建应该是没有问题了，基本能够正常运转。
***
***
##  其他设置  
下面来说一下其他不常用设置 
###  附件  
修改附件的上传大小限制。  
设置-系统-附件
###  经办人  
“经办人”字段是系统预定义的字段；如果一个用户拥有“执行工作流”的权限，则此用户即可拥有改变“经办人”的权限；经办人列表是从项目的用户列表中读取出来的。
###  系统面板
系统设置-系统-系统面板  
系统面板可以在登录后查看自定义的小配件，推荐favourite Filters模块，这样可以快速抵达自己关注的问题。  
Favourite filters设置在下面[过滤器](#过滤器)讲述。
###  过滤器  
过滤器可以对系统中的数据进行过滤，其支持自定义字段，并支持收藏以便于下次快速访问结果集。  
在问题列表中，basic模式下，可以使用可视化界面进行过滤；advanced模式下，可以使用类似SQL的形式做更加复杂的过滤。
过滤完成，点击Save as，保存过滤器；保存完毕，在过滤器管理界面（find filters)可查看或维护。  
过滤器可以在编辑动作中设置是否共享以及共享的对象，如果用户无法将自定义过滤器共享与其他对象，需要检查[全局权限](#全局权限)中关于“创建共享的对象”的权限。
如果系统面板中有favorite filters小部件，则加入收藏的过滤器就可以在首页进行展示，点击可以直达过滤的结果集。
###  邮件定时发送系统事件  
我们可以对系统中的事件进行订阅，以达到系统按照指定事件发送问题列表至邮箱的目的。  
需要完成订阅功能，首先需要在[过滤器](#过滤器)中定义过滤器，然后在过滤器管理功能中点击“订阅”操作。。  
***
###  列表字段调整  
JIRA中定义的字段（包含预定义或自定义）都能显示在项目的事件列表中，不管这个项目的操作界面是否使用了；所以我们可能需要对其的展示进行一些微调
#### 列排序调整
全局调整：管理员用户进入某一项目，再进入问题列表，选中列头拖动即可；此处调整后即是所有用户的缺省列排序。  
私有调整：非管理员的个人用户进入某一项目，拖动列头。  
需要注意的是，JIRA并不支持每个项目有特定的排序，所以调整一个后，所有的项目都是按照此排序进行展示。
#### 列显示调整
正如[列表字段调整](#列表字段调整)中讲述的"JIRA中定义的字段（包含预定义或自定义）都能显示在项目的事件列表中，不管这个项目的操作界面是否使用"，那么如果在项目中，不想看到无关的字段，系统支持调整。  
全局调整： 管理员进入某一项目，再进入问题列表，点击列头右上角“Columns”，然后点击“system”进入系统设置模式，调整全局列展示风格。  
私有调整：非管理员个人用户，设置“my default"风格。  
需要注意的是，JIRA并不支持每个项目有特定的展示风格，所以调整一个后，所有的项目都是按照此设置进行展示。
#### 列表显示值调整
如果某个字段设置了默认值，但是没有被此项目所使用的操作界面使用，那么默认情况下，录入后在列表中这个字段是有值的，如果不想有值，需要在[字段配置](#字段配置)中设置。
***
###  邮件模板注意事项
记录一下两个个人配置的坑：  
1、发现编辑备注后发送的邮件上面没有明确提示，本来想着去改邮件模板；
后来参考了默认邮件通知方案，发现在“已添加备注”和“备注被编辑”没有配置通知，导致编辑后直接发送的是更新的邮件模板。  
2、发现配置了自定义事件发送的邮件标题是created，不能分清到底是创建还是更新，这里需要注意的是创建事件的时候选择模板，如果选择“issue updated“则可以显示更新前后的值的变化。

###  批量操作
管理员用户进入项目列表，右上角”tools“    
###  解决结果
设置-问题-解决结果  
设置解决结果可以在JIRA报表中直观的查看问题解决结果   
注意解决结果和状态是相对独立的概念  
#### 工作流执行修改解决结果
如果需要工作流执行后将解决结果修改为指定值，需要进入工作流，编辑模式，选中工作流动作，点击右边“结果处理”-“Add post function”-“更新问题字段”-“选择解决结果”。  
###  修改日期显示
设置-系统-外观  
”日期/时间格式”栏位。  
