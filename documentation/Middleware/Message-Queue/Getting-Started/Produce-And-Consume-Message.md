# 生产和消费消息
在控制台创建消息主题（topic）后，用户可以通过控制台或者调用SDK或者API来发送消息。
控制台不支持批量发送，主要用于检验资源的可用性，生产环节建议使用SDK或者API来进行消息的发送。</br>
    
消息发送成功后，需要根据绑定的Consumer Group ID进行消息的消费，需要调用SDK/API进行。

## 前提条件
- 已经创建topic及订阅关系，并且状态处于服务中。

## 注意事项
- 对于单个topic的每秒事务处理数最大为5000TPS
- 消息的生命周期为3天
- 消息体大小为256KB

## 方式一：通过控制台生产消息
1. 在Topic管理页面中，找到想要发送消息的topic，在操作中可以选择发送消息。

2. 输入Message Body、Business ID和tag，并且如果想要发送延时消息可以设置消息延迟时间。

3. 消息发送成功，会返回消息发送成功通知和消息的Message ID，点击消息详情可以进行查看。

### 说明：

1. 消息的生命周期为3天，超过生命周期消息删除无法恢复，Message Body的最大支持256Kb。

2. 消息的延迟时间范围为：0~3600秒。

3. 订阅者tag的规则说明：tag是消息消费者对于消息的筛选，当消费者设置了tag时，有相同tag的消息才能被消费者消费，如果没有设置tag，则消费者对消息不做筛选。

- 对于消息1，没有消息tag，消费者有tag，则该消费者不匹配，收不到消息；

- 对于消息2， 消息有tag，消费者没有tag，投递时消息不用匹配，消费者都能收到消息；

- 对于消息3，消息有tag，消费者也有tag的时候，两者匹配的，才能收到消息；

- 对于消息4，消息没有tag，消费者也没有tag，投递后，所有消费者都能收到消息。


## 方式二：通过SDK/API生产和消费消息

以Java SDK为例进行说明，其他方式及开发语言请参考其他章节。

1. 引入依赖
```XML
<dependency>
   <groupId>com.jdcloud</groupId>
   <artifactId>jcq-java-sdk</artifactId>
   <version>${jcq.sdk.version}</version>
</dependency>
```
2. 发送和订阅代码部分请参考demo示例：[jcq-sdk-demo.zip](http://jcq-inuse-important-cannotdelete.oss.cn-north-1.jcloudcs.com/jcq-sdk-demo.zip)。

### 说明：

1. 服务端向订阅者（接收端）推送消息，保证至少一次，最多尝试16次，在出现错误时的重试策略为：间隔依次为5, 10, 20, 30, 40, 50, 60, 120, 180, 240, 300, 360, 420, 720, 1440, 2880秒。

2. 服务端在尝试推送消息16次均失败后，消息会进入死信队列，在死信队列保存时间为消息的生命周期3天，超过消息生命周期消息不可恢复、重发。

3. Spring框架下消息队列 JCQ的集成，请参考demo示例：[jcq-spring-demo.zip](http://jcq-inuse-important-cannotdelete.oss.cn-north-1.jcloudcs.com/jcq-spring-demo.zip)。

## 消费者特性

同一ConsumerGroup下，Consumer数目是否必须小于等于Partition数目吗？

* 是，以Kafka、RocketMQ等为代表：

  利：避免Ack Offset 加锁；避免消息重复，严格保证顺序；
  
  弊：堆积情况下不能通过增加Consumer来加速消息消费慢消息，一条慢消息导致后面的消息都不能被及时处理。
  
* 否，JCQ

  利： 堆积情况下可以通过增加Consumer加速消费应对慢消息的问题；
  
  弊：不能保证消息严格顺序，可能造成消息重复。


