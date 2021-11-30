# describeIpResourceProtectInfo


## 描述
查询公网 IP 的攻击记录, 仅支持 ipv4. (已废弃, 建议使用 <a href='http://docs.jdcloud.com/anti-ddos-basic/api/describeattacklogs'>describeAttackLogs</a> 接口)


## 请求方式
GET

## 请求地址
https://baseanti.jdcloud-api.com/v1/regions/{regionId}/ipResources/{ip}/protectInfo

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域编码. 基础防护已支持华北-北京, 华东-宿迁, 华东-上海, 华南-广州|
|**ip**|String|True| |基础防护已防护的公网 IP, 仅支持 ipv4 格式. <br>- 使用 <a href='http://docs.jdcloud.com/anti-ddos-basic/api/describeelasticipresources'>describeElasticIpResources</a> 接口查询基础防护已防护的私有网络弹性公网 IP<br>- 使用 <a href='http://docs.jdcloud.com/anti-ddos-basic/api/describecpsipresources'>describeCpsIpResources</a> 接口查询基础防护已防护的云物理服务器公网 IP 和 弹性公网 IP<br>- 使用 <a href='http://docs.jdcloud.com/anti-ddos-basic/api/describeccsipresources'>describeCcsIpResources</a> 接口查询基础防护已防护的托管区公网 IP|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**start**|Integer|False| |限制查询的开始范围|
|**limit**|Integer|False| |限制查询的记录数|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](describeipresourceprotectinfo#result)| |
|**requestId**|String| |
|**error**|[Error](describeipresourceprotectinfo#error)| |

### <div id="error">Error</div>
|名称|类型|描述|
|---|---|---|
|**err**|[Err](describeipresourceprotectinfo#err)| |
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
|**dataList**|[IpResourceProtectInfo[]](describeipresourceprotectinfo#ipresourceprotectinfo)| |
### <div id="ipresourceprotectinfo">IpResourceProtectInfo</div>
|名称|类型|描述|
|---|---|---|
|**startTime**|String|攻击开始时间|
|**endTime**|String|攻击结束时间|
|**status**|Integer|安全状态. <br>- 0: 安全<br>- 1: 清洗<br>- 2: 黑洞|
|**cause**|Integer|触发原因. <br>- 0: 未知<br>- 1: 四层<br>- 2: 七层<br>- 3: 四和7层|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
