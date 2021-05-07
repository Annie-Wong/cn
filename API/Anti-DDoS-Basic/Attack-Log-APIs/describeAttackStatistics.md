# describeAttackStatistics


## 描述
攻击情况统计

## 请求方式
GET

## 请求地址
https://baseanti.jdcloud-api.com/v1/describeAttackStatistics


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**startTime**|String|True| |开始时间, UTC 时间, 格式: yyyy-MM-dd'T'HH:mm:ssZ|
|**endTime**|String|True| |结束时间, UTC 时间, 格式: yyyy-MM-dd'T'HH:mm:ssZ|
|**ip**|String[]|False| |基础防护已防护的公网 IP, ip 不为空时, 统计 ip 对应的攻击情况, ip 为空时, 统计用户所有公网 IP 的攻击情况. <br>- 使用 <a href='http://docs.jdcloud.com/anti-ddos-basic/api/describeelasticipresources'>describeElasticIpResources</a> 接口查询基础防护已防护的私有网络弹性公网 IP. <br>- 使用 <a href='http://docs.jdcloud.com/anti-ddos-basic/api/describecpsipresources'>describeCpsIpResources</a> 接口查询基础防护已防护的云物理服务器公网IP 和 弹性公网 IP. <br>- 使用 <a href='http://docs.jdcloud.com/anti-ddos-basic/api/describeccsipresources'>describeCcsIpResources</a> 接口查询基础防护已防护的托管区公网 IP|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](describeattackstatistics#result)| |
|**requestId**|String| |
|**error**|[Error](describeattackstatistics#error)| |

### <div id="error">Error</div>
|名称|类型|描述|
|---|---|---|
|**err**|[Err](describeattackstatistics#err)| |
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
|**attackCount**|Integer|攻击次数|
|**blackHoleCount**|Integer|黑洞次数|
|**peak**|Double|攻击流量峰值|
|**unit**|String|攻击流量单位|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
