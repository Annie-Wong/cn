# modifyWhiteListRuleOfWebRule


## 描述
修改网站类规则的白名单规则

## 请求方式
PATCH

## 请求地址
https://ipanti.jdcloud-api.com/v1/regions/{regionId}/instances/{instanceId}/webRules/{webRuleId}/webWhiteListRules/{webWhiteListRuleId}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |区域 ID, 高防不区分区域, 传 cn-north-1 即可|
|**instanceId**|String|True| |高防实例 Id|
|**webRuleId**|String|True| |网站规则 Id|
|**webWhiteListRuleId**|String|True| |网站类规则的白名单规则 Id|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**webWhiteListRuleSpec**|[WebWhiteListRuleSpec](modifywhitelistruleofwebrule#webwhitelistrulespec)|True| |修改网站类规则的白名单规则请求参数|

### <div id="webwhitelistrulespec">WebWhiteListRuleSpec</div>
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**name**|String|True| |白名单规则名称|
|**mode**|Integer|True| |模式:<br>- 0: uri<br>- 1: ip<br>- 2: cookie<br>- 3: geo<br>- 4: header|
|**key**|String|False| |匹配 key, mode 为 cookie 和 header 时必传. <br>- mode 为 cookie 时, 传 cookie 的 name<br>- mode 为 header 时, 传 header 的 key|
|**value**|String|True| |匹配 value. <br>- mode 为 uri 时, 传要匹配的 uri<br>- mode 为 ip 时, 传引用的 ip 黑白名单 Id<br>- mode 为 cookie 时, 传 cookie 的 value<br>- mode 为 geo 时, 传 geo 区域编码以 ',' 分隔的字符串. 查询 <a href='http://docs.jdcloud.com/anti-ddos-pro/api/describewebrulewhitelistgeoareas'>describeWebRuleWhiteListGeoAreas</a> 接口获取可设置的地域编码列表<br>- mode 为 header 时, 传 header 的 value|
|**pattern**|Integer|False| |匹配规则, mode 为 uri, cookie 和 header 时必传. 支持以下匹配规则: <br>- 0: 完全匹配<br>- 1: 前缀匹配<br>- 2: 包含<br>- 3: 正则匹配<br>- 4: 后缀匹配|
|**action**|Integer|True| |命中后处理动作. <br>- 0: 放行<br>- 1: CC 防护|
|**status**|Integer|True| |规则状态. <br>- 0: 关闭<br>- 1: 开启|

## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](modifywhitelistruleofwebrule#result)| |
|**requestId**|String| |
|**error**|[Error](modifywhitelistruleofwebrule#error)| |

### <div id="error">Error</div>
|名称|类型|描述|
|---|---|---|
|**err**|[Err](modifywhitelistruleofwebrule#err)| |
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
|**code**|Integer|修改结果, 0: 修改失败, 1: 修改成功|
|**message**|String|修改失败时给出具体原因|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
