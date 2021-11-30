# describeIpResourceInfo


## 描述
查询公网 IP 安全信息, 仅支持 ipv4. (已废弃, 建议使用 <a href='http://docs.jdcloud.com/anti-ddos-basic/api/describeipsafetyinfo'>describeIpSafetyInfo</a> 接口)


## 请求方式
GET

## 请求地址
https://baseanti.jdcloud-api.com/v1/regions/{regionId}/ipResources/{ip}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域编码. 基础防护已支持华北-北京, 华东-宿迁, 华东-上海, 华南-广州|
|**ip**|String|True| |基础防护已防护的公网 IP, 仅支持 ipv4 格式. <br>- 使用 <a href='http://docs.jdcloud.com/anti-ddos-basic/api/describeelasticipresources'>describeElasticIpResources</a> 接口查询基础防护已防护的私有网络弹性公网 IP<br>- 使用 <a href='http://docs.jdcloud.com/anti-ddos-basic/api/describecpsipresources'>describeCpsIpResources</a> 接口查询基础防护已防护的云物理服务器公网 IP 和 弹性公网 IP<br>- 使用 <a href='http://docs.jdcloud.com/anti-ddos-basic/api/describeccsipresources'>describeCcsIpResources</a> 接口查询基础防护已防护的托管区公网 IP|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](describeipresourceinfo#result)| |
|**requestId**|String| |
|**error**|[Error](describeipresourceinfo#error)| |

### <div id="error">Error</div>
|名称|类型|描述|
|---|---|---|
|**err**|[Err](describeipresourceinfo#err)| |
### <div id="err">Err</div>
|名称|类型|描述|
|---|---|---|
|**code**|Long|同http code|
|**details**|Object| |
|**message**|String| |
|**status**|String|具体错误|
### <div id="result">Result</div>
|名称|类型|描述|
|---|---|---|
|**data**|[IpResourceInfo](describeipresourceinfo#ipresourceinfo)| |
### <div id="ipresourceinfo">IpResourceInfo</div>
|名称|类型|描述|
|---|---|---|
|**ip**|String|公网 IP 地址|
|**safeStatus**|Integer|安全状态. <br>- 0: 安全<br>- 1: 清洗<br>- 2: 黑洞|
|**region**|String|公网 IP 所属地域编码|
|**blackHoleThreshold**|Long|黑洞阈值，单位 bps|
|**cleanThresholdBps**|Long|触发清洗的流量速率，单位 bps|
|**cleanThresholdPps**|Long|触发清洗的包速率，单位 pps|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
