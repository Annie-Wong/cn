# describeWebRuleWhiteListUsage


## 描述
查询网站类防护规则的白名单用量信息

## 请求方式
GET

## 请求地址
https://ipanti.jdcloud-api.com/v1/regions/{regionId}/instances/{instanceId}/webRules/{webRuleId}:describeWebRuleWhiteListUsage

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |区域 ID, 高防不区分区域, 传 cn-north-1 即可|
|**instanceId**|String|True| |高防实例 Id|
|**webRuleId**|String|True| |网站规则 Id|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](describewebrulewhitelistusage#result)| |
|**requestId**|String| |
|**error**|[Error](describewebrulewhitelistusage#error)| |

### <div id="error">Error</div>
|名称|类型|描述|
|---|---|---|
|**err**|[Err](describewebrulewhitelistusage#err)| |
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
|**allocatedNum**|Integer|已配置的白名单规则数量|
|**activeNum**|Integer|开启的白名单规则数量|
|**surplusAllocateNum**|Integer|还可添加的白名单规则数量|
|**maxAllocateNum**|Integer|最多可添加的白名单规则数量|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
