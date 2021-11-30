# deleteForwardRule


## 描述
删除非网站规则, 批量操作时, 返回 result.code 为 1 表示操作成功, 为 0 时可能全部失败, 也可能部分失败

## 请求方式
DELETE

## 请求地址
https://ipanti.jdcloud-api.com/v1/regions/{regionId}/instances/{instanceId}/forwardRules/{forwardRuleId}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |区域 ID, 高防不区分区域, 传 cn-north-1 即可|
|**instanceId**|String|True| |高防实例 Id|
|**forwardRuleId**|String|True| |转发规则 Id|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](deleteforwardrule#result)| |
|**requestId**|String| |
|**error**|[Error](deleteforwardrule#error)| |

### <div id="error">Error</div>
|名称|类型|描述|
|---|---|---|
|**err**|[Err](deleteforwardrule#err)| |
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
|**code**|Integer|0: 删除规则失败, 1: 删除规则成功|
|**message**|String|删除规则失败时给出具体原因|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
