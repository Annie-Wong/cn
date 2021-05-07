# addServers


## 描述
添加后端服务器

## 请求方式
PUT

## 请求地址
https://cps.jdcloud-api.com/v1/regions/{regionId}/serverGroups/{serverGroupId}/servers

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域ID，可调用接口（describeCPSLBRegions）获取云物理服务器支持的地域|
|**serverGroupId**|String|True| |服务器组ID|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**clientToken**|String|False| |由客户端生成，用于保证请求的幂等性，长度不能超过36个字符；<br/><br>如果多个请求使用了相同的clientToken，只会执行第一个请求，之后的请求直接返回第一个请求的结果<br/><br>|
|**serverSpec**|[ServerSpec[]](addservers#serverspec)|True| |后端服务器配置|

### <div id="serverspec">ServerSpec</div>
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**instanceId**|String|False| |后端云物理服务器ID|
|**port**|Integer|False| |端口|
|**weight**|Integer|False| |后端云物理服务器权重|

## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](addservers#result)| |
|**requestId**|String| |

### <div id="result">Result</div>
|名称|类型|描述|
|---|---|---|
|**serverIds**|String[]|后端服务器ID|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
|**400**|Bad request|
|**404**|Not found|
|**500**|Internal server error|
|**503**|Service unavailable|
