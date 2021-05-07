# deleteCCProtectionRuleOfWebRule


## 描述
删除网站规则的 CC 防护规则

## 请求方式
DELETE

## 请求地址
https://ipanti.jdcloud-api.com/v1/regions/{regionId}/instances/{instanceId}/webRules/{webRuleId}/ccProtectionRules/{ccProtectionRuleId}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |区域 ID, 高防不区分区域, 传 cn-north-1 即可|
|**instanceId**|String|True| |高防实例 Id|
|**webRuleId**|String|True| |网站规则 Id|
|**ccProtectionRuleId**|String|True| |网站类规则的 CC 防护规则 Id|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](deleteccprotectionruleofwebrule#result)| |
|**requestId**|String| |
|**error**|[Error](deleteccprotectionruleofwebrule#error)| |

### <div id="error">Error</div>
|名称|类型|描述|
|---|---|---|
|**err**|[Err](deleteccprotectionruleofwebrule#err)| |
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
|**code**|Integer|0: 删除失败, 1: 删除成功|
|**message**|String|删除失败时给出具体原因|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
