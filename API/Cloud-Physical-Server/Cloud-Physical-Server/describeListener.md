# describeListener


## 描述
查询监听器详情

## 请求方式
GET

## 请求地址
https://cps.jdcloud-api.com/v1/regions/{regionId}/listeners/{listenerId}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域ID，可调用接口（describeCPSLBRegions）获取云物理服务器支持的地域|
|**listenerId**|String|True| |监听器ID|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](describelistener#result)| |
|**requestId**|String| |

### <div id="result">Result</div>
|名称|类型|描述|
|---|---|---|
|**listener**|[Listener](describelistener#listener)|监听器详细信息|
### <div id="listener">Listener</div>
|名称|类型|描述|
|---|---|---|
|**listenerId**|String|监听器ID|
|**loadBalancerId**|String|负载均衡ID|
|**protocol**|String|协议|
|**port**|Integer|端口|
|**algorithm**|String|调度算法|
|**stickySession**|String|会话保持状态，取值on|off|
|**realIp**|String|获取真实ip|
|**status**|String|状态|
|**name**|String|名称|
|**description**|String|描述|
|**healthCheck**|String|健康检查状态，取值on|off|
|**healthCheckTimeout**|Integer|健康检查响应的最大超时时间，单位s|
|**healthCheckInterval**|Integer|健康检查响应的最大间隔时间，单位s|
|**healthyThreshold**|Integer|健康检查结果为success的阈值|
|**unhealthyThreshold**|Integer|健康检查结果为fail的阈值|
|**healthCheckIp**|String|健康检查ip|
|**serverGroupId**|String|服务器组id|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
|**400**|Bad request|
|**404**|Not found|
|**500**|Internal server error|
|**503**|Service unavailable|
