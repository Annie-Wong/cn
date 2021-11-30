# describeCCAttackLogs


## 描述
查询 CC 攻击日志

## 请求方式
GET

## 请求地址
https://ipanti.jdcloud-api.com/v1/regions/{regionId}/attacklog:describeCCAttackLogs

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |区域 ID, 高防不区分区域, 传 cn-north-1 即可|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**pageNumber**|Integer|False| |页码, 默认为1|
|**pageSize**|Integer|False| |分页大小, 默认为10, 取值范围[10, 100]|
|**startTime**|String|True| |开始时间, 只能查询最近 90 天以内的数据, UTC 时间, 格式: yyyy-MM-dd'T'HH:mm:ssZ|
|**endTime**|String|False|当前时间|查询的结束时间, UTC 时间, 格式: yyyy-MM-dd'T'HH:mm:ssZ|
|**instanceId**|String[]|False| |高防实例 ID|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](describeccattacklogs#result)| |
|**requestId**|String| |
|**error**|[Error](describeccattacklogs#error)| |

### <div id="error">Error</div>
|名称|类型|描述|
|---|---|---|
|**err**|[Err](describeccattacklogs#err)| |
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
|**dataList**|[CCAttackLog[]](describeccattacklogs#ccattacklog)| |
|**currentCount**|Integer|当前页数量|
|**totalCount**|Integer|实例总数|
|**totalPage**|Integer|总页数|
### <div id="ccattacklog">CCAttackLog</div>
|名称|类型|描述|
|---|---|---|
|**attackId**|String|CC 攻击记录Id|
|**attackTraffic**|Double|攻击流量大小|
|**blackHole**|Integer|是否触发黑洞, 0否 1是|
|**startTime**|String|攻击开始时间|
|**endTime**|String|攻击结束时间|
|**unit**|String|流量单位, bps、Kbps、Mbps、Gbps|
|**instanceId**|String|高防实例id|
|**name**|String|高防实例名称|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
