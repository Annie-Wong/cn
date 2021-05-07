# 配置管理
配置管理，提供给用户对应用进行配置的服务。配置的类型包含：

| 类型	| 说明	| 
| :- | :- | 
|  应用配置	|  对具体的某一个应用生效。 在优先级上，应用配置优先于全局配置。	|  
|  全局配置	|  对命名空间生效。 	|  
 
提供的功能包含：

| 功能	| 说明	| 
| :- | :- | 
|  创建配置	|  可根据需要创建应用配置或全局配置。	|  
|  多版本	|  每个配置可以维护多个版本。以最新发布的版本号为生效版本。 	|  
|  发布配置	|  发布配置到某个注册中心后生效。注意，对于使用JDSF平台部署的K8S应用，如果在部署时并未选择使用JDSF平台注册中心实现应用的注册发现，那么配置将无法发布到该K8S应用上。	|  
|  发布历史	|  每个配置的发布历史清单。	|  
|  回滚	|  回滚至上一个版本。	| 
|  配置文件导入/导出	|  支持对配置文件的导入和导出。	| 




## 操作步骤

### 配置管理列表

 ![](../../../../../image/Internet-Middleware/JD-Distributed-Service-Framework/config-list-new.png)
 

### 创建配置

#### 创建应用配置

第1步：先选择可用区region，再点击新建配置。
 
第2步：填写信息。

1、注意同一服务上，不能创建同名配置。


2、类型选择 创建应用配置，并且选择目标应用。注意这里的应用配置功能仅对 Spring Cloud 应用生效。


![](../../../../../image/Internet-Middleware/JD-Distributed-Service-Framework/pzgl-xjpz-1.png)
  
  
第3步：发布配置  

选择要发布的配置，并点击发布。

![](../../../../../image/Internet-Middleware/JD-Distributed-Service-Framework/pzgl-fb-yypz.png)
  
部分字段内容说明：

| 字段	| 说明	| 
| :- | :- | 
|  Profile	|  是隔离配置文件的方式，仅允许配置在指定环境下生效。该参数将作用于路由策略。若无特殊要求可选择默认值。  	|  
|  配置存储	|  配置存储的物理位置	|
|  资源名称	|  配置存储的具体存储位置. 	|  


####  创建全局配置

第1步：先选择可用区region，再点击新建配置。
 
第2步：填写信息。

1、注意同一服务上，不能创建同名配置。

2、类型选择 创建全局配置。

![](../../../../../image/Internet-Middleware/JD-Distributed-Service-Framework/pzgl-xjpz-2.png)
  
  
第3步：发布配置  

选择要发布的配置，并点击发布。

![](../../../../../image/Internet-Middleware/JD-Distributed-Service-Framework/pzgl-fb-yypz.png)
  
  
### 查看配置项的版本信息

点击配置项的名称。进入版本列表页，可查看该配置发布的所有版本。
![](../../../../../image/Internet-Middleware/JD-Distributed-Service-Framework/config-vision.png)
   
   
点击版本号名称可查看版本详情。
![](../../../../../image/Internet-Middleware/JD-Distributed-Service-Framework/config-vision-detail-new.png)



### 查看配置的发布历史
选择配置管理列表中某条配置，可查看该条配置的发布历史记录。
![](../../../../../image/Internet-Middleware/JD-Distributed-Service-Framework/config-vision-history-new.png)


### 生成新版本
第1步： 进入配置管理列表，点击配置项的名称，进入该配置的版本管理页。
![](../../../../../image/Internet-Middleware/JD-Distributed-Service-Framework/pzgl-xdlb.png)
 

第2步：点击操作中的生成新版本，进入版本编辑页。保存后生成新版本。

- 这里默认的父版本号为您上一步中选择的版本的版本号。

- 默认展示父版本内容。

- 新版本号需要大于所有老版本号。
![](../../../../../image/Internet-Middleware/JD-Distributed-Service-Framework/config-vision-add-new.png)
  

第3步： 发布新版本。

- 发布后，新版本会替代原有版本作为线上版本。

- 在版本修订列表中，需至少保留1条版本记录。如您需要删除所有记录，请在上一级“配置管理”中删除整条配置记录。

### 配置文件导入/导出

1、导入。可在新建配置时，直接导入文件。

![](../../../../../image/Internet-Middleware/JD-Distributed-Service-Framework/pzgl-xjpz-1.png)


2、导出。入口：配置文件>选择某个版本号查看详情>在详情页中有导出的配置

![](../../../../../image/Internet-Middleware/JD-Distributed-Service-Framework/pzgl-xjpz-dc.png)
