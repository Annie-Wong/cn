# 安全运营中心定义 

### 产品定义

​		安全运营中心（Security Operation Center，SOC）是京东云云原生的统一安全运营与管理平台，通过统一资产管理、统一身份管理、统一威胁管理构建了多云场景下安全托管体系，通过安全可视化、安全防范、威胁检测、调查响应实现了多云场景安全运营闭环，通过全量日志分析、未知威胁取证、黑客攻击溯源提供了多云场景下的安全对抗能力；同时满足云上监管合规要求。

​		作为态势感知产品的升级版，**京东云安全运营中心产品**致力于在多云场景下，为用户构建完整的资产管理中心，在用户云内外资产完整管理的前提下实现统一的安全运营。并针对各种类型的资产进行安全状态监控，当出现安全告警或事件时，能够及时定位到相关资产，并通过资产管理可以定位到资产的归属人与归属地。能够很好地做到有效发现问题、及时定位到人、追踪跟进解决。同时提供多云场景下的安全托管服务，满足各类政企客户“重保期间安全服务托管、非重保期间日常安全运营维护”的不同时期的安全运营需要。

### **产品解决哪些痛点？**

概述：**解决安全运营人员在安全风险发生的**事前、事中、事后**面临的六大痛点**。

#### 事前不可视

- 安全态势缺乏直观呈现（无法知晓资产是否受到攻击、受到何种类型的攻击、具有何种严重程度和危险等级）

- 全局资产缺乏实时感知（各类安全设备和系统投资巨大，但缺乏资产状态变更、资产新增的及时发现和感知）

#### **事中不可控**

- 未知风险缺乏有效检测（针对层出不穷的新型安全威胁，不能做到及时发现、将威胁拒之门外、防患于未然）

- 突发事件缺乏敏捷响应（告警威胁等信息难以得到及时验证，无法形成“防护、检测、响应”安全运营闭环）

#### **事后不可察**

- 威胁攻击缺乏回溯取证（安全事件频发，想从事件中总结教训，如何有效的进行追溯分析和取证）

- 日常运营缺乏量化评估（针对安全运营人员处理的安全事件数量、质量，缺乏有效量化评估体现）

### **产品包含哪些功能？**

#### **全局可视**

- 资产安全仪表盘

  提供托管账号统计看板、整体安全态势评分、资产风险状态、安全产品状态、风险快捷处置等功能，提升安全治理效率，通过攻击面概览面板，有效发现当前对外暴露的业务系统存在违规端口、应用，以及攻击总次数、攻击源IP、攻击网段排名、攻击地理位置分布等

- 态势感知大屏

  应用于618、双11、重保、护网等场景安全态势风险监控，帮助安全运营团队及时发现风险，并做出有效的安全处置决策

- 安全运营报表

  支持自定义安全报表，包括但不限于报表logo、生成时间、统计时间范围，包含报表模块

#### **安全防范**

- 策略管理

  制定相应检查策略、周期性监控各类资产健康状态、及时发现漏洞隐患

- 漏洞管理

  针对当前资产中存在各类漏洞、给出相应修复建议、帮助用户及时修复

- 云产品基线核查

  帮助用户及时发现各类云产品配置的风险并提供相应的修复方案

- 主机合规基线检测

  多维检测主机安全配置，预防由于配置疏忽导致入侵事件发生
  
- 攻击面分析

  提供当前业务系统对外开放的端口、应用以及攻击源IP定位分析

#### **威胁检测**

- 安全告警

  提供覆盖网络层、主机层35种攻击告警日志，并且提供详细入侵证据以及修复建议

- 安全事件

  依托洛克希德马丁的攻击链模型，将海量告警有效归纳，帮助用户快速发现入侵行为

#### **调查响应**

- 全量日志分析

  提供企业级用户日志集中管理和搜索关联分析能力，支持用户自定义威胁检索，告警设置功能，提升安全分析效率

- 自动化攻击溯源

  可视化关联分析，对基础数据进行深度挖掘，自动输出关联分析后的溯源路径，降低安全分析门槛，提升运营效率
  
- 用户实体行为分析UEBA

  支持针对NAT网关、数据库审计、堡垒机三类云上用户使用的产品进行使用过程追溯，发现用户异常操作行为


#### **安全托管**

- 托管服务

  面向重大活动用户可以放心托管、托管行为全程审计、更为安全可控

### **产品具备哪些亮点？**

#### **打造当前业界最全面的安全资产中心**

- **提供2种资产接入模式**
  - 自动同步
  - 手动导入

- **标记4种资产预制分组**
  - 单类资产总量
  - 存在风险的资产
  - 未受保护的资产
  - 待确认的资产
- **覆盖8种资产类型分布**
  - 云主机
  - 容器
  - 网站
  - 物理服务器
  - 公网IP
  - 内网IP
  - 其它云产品
  - 其它物理设备
- **监控8种资产安全指标**
  - 终端安全保护
  - 网络入侵检测
  - 漏洞扫描巡检
  - SSL证书保护
  - WAF应用防护
  - DDoS基础防护
  - IP高防
  - 数据库审计

#### **构建业界最为可靠放心安全托管服务**

- **托管行为全程审计、重大活动安全可控**

- **攻击风险大屏呈现、威胁攻击追根溯源**

- **日常治理省时省力、漏洞隐患集中呈现**

**（五）交付用户哪些价值？**

- **初步构建安全托管体系**

  统一资产管理、统一身份管理、统一漏洞管理

- **完整打造安全运营闭环**

  防范、检测、响应、可视

- **提供基础安全对抗能力**

  全量日志分析、潜在威胁取证