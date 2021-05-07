## 日志监控配置案例——业务应用日志监控

本节将通过一个实际的案例，完成一个日志监控的配置。旨在通过描述整个配置过程让用户更容易地理解日志字段监控的功能。

### 一、监控配置目标：

1.对用户部署在京东云服务器上的某款游戏支付日志进行字段监控，以便了解用户支付情况。

2.需要对每分钟内所有支付失败的订单进行数量统计，当每分钟内支付失败的订单达到50笔时即支付系统发生异常，需要设置报警通知相关人员Jason。日志中出现paymentStatus=failed即为支付失败。

### 二、监控方案设置：

达成上述监控配置目标的设置方案如下所示：

1.选择该业务应用日志所在的日志集，进入日志主题列表。

![](https://raw.githubusercontent.com/jdcloudcom/cn/zhangwenjie-only/image/LogService/bestpractice/bestmonitor01.jpg)

2.点击该日志主题下的子菜单“日志监控”，点击“日志监控”后方的“添加”按钮，或者进入监控任务列表页，点击“新建监控任务”按钮。

![](https://raw.githubusercontent.com/jdcloudcom/cn/zhangwenjie-only/image/LogService/bestpractice/bestmonitor02.jpg)

3.输入监控任务名称

4.筛选设置中，选择键值筛选，输入键值筛选的条件为**paymentStatus = "failed"**

5.监控指标设置中，统计项选择“**日志原文**”，统计方式选择“计数”，监控指标名称输入为：**failed_count**，单位选择**count**。

6.打开日志测试，可以从从当前的日志主题获取最新的日志数据，也可以选择自定义日志数据，手动输入两条日志数据。

```
{"paymentStatus": "failed"}
{"paymentStatus":"succeed"}
{"paymentStatus": "failed"}
{"paymentStatus":"succeed"}
{"paymentStatus": "failed"}
{"paymentStatus":"succeed"}
```
7.点击"测试"，可以看到测试数据结果中显示：从样本日志中的6条数据中得出日志原文的计数为3count。结果列表中显示符合条件的样本中的日志数据。符合预期，点击确定，完成配置。

### 三、报警方案设置

上述监控配置中的报警目标为：当每分钟内支付失败的订单达到50笔时即支付系统发生异常，需要设置报警通知相关人员Jason。

1.选择监控任务"**支付失败次数监控**"后方的"**监控图**"，点击监控图进入查看监控图页面。

2.点击右上方的”可前往云监控设置报警规则“中的设置报警规则，跳转至云监控中的自定义监控的页面。

3.对日志集下的日志主题中的指标名称为“failed_count”的指标设置告警，当该指标统计周期为1min时的值大于50时，触发报警，报警联系人选择Jason。点击“完成”，完成报警规则的设置。



