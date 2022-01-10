# describeDedicatedHosts


## 描述
查询一台或多台专有宿主机的详细信息。

### 接口说明
- 使用 `filters` 过滤器进行条件筛选，每个 `filter` 之间的关系为逻辑与（AND）的关系。
- 单次查询最大可查询100条专有宿主机实例数据。
- 尽量一次调用接口查询多条数据，不建议使用该批量查询接口一次查询一条数据，如果使用不当导致查询过于密集，可能导致网关触发限流。
- 由于该接口为 `GET` 方式请求，最终参数会转换为 `URL` 上的参数，但是 `HTTP` 协议下的 `GET` 请求参数长度是有大小限制的，使用者需要注意参数超长的问题。


## 请求方式
GET

## 请求地址
https://dh.jdcloud-api.com/v1/regions/{regionId}/dedicatedHosts

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|是| |地域ID|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**pageNumber**|Integer|否 |1|页码；默认为1|
|**pageSize**|Integer|否|20|分页大小；默认为20；取值范围[10, 100]|
|**filters**|[Filter[]](#filter)|否| |dedicatedHostId - 专有宿主机ID，精确匹配，支持多个<br>az - 可用区，精确匹配，支持多个<br>status - 专有宿主机状态，精确匹配，支持多个，<a href="http://docs.jdcloud.com/dedicated-hosts/api/dh_status">参考专有宿主机状态</a><br>name - 专有宿主机名称，模糊匹配，支持单个<br>dedicatedPoolId - 专有宿主机池ID，精确匹配，支持多个<br>dedicatedHostType - 专有宿主机机型，精确匹配，支持多个<br>|

### <div id="Filter">Filter</div>
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**name**|String|是 | |过滤条件的名称|
|**operator**|String|否| |过滤条件的操作符，默认eq|
|**values**|String[]|是 | |过滤条件的值|

## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](#result)| |
|**requestId**|String| |

### <div id="Result">Result</div>
|名称|类型|描述|
|---|---|---|
|**dedicatedHosts**|[DedicatedHost[]](#dedicatedhost)| |
|**totalCount**|Number| |
### <div id="DedicatedHost">DedicatedHost</div>
|名称|类型|描述|
|---|---|---|
|**dedicatedHostId**|String|专有宿主机ID|
|**name**|String|专有宿主机名称|
|**az**|String|专有宿主机所在可用区|
|**dedicatedHostType**|String|专有宿主机机型|
|**description**|String|专有宿主机描述|
|**status**|String|专有宿主机状态，<a href="http://docs.jdcloud.com/dedicated-hosts/api/dh_status">参考专有宿主机状态</a>|
|**dedicatedPoolId**|String|专有宿主机所在的专有宿主机池ID|
|**logicRack**|Integer|专有宿主机所在的逻辑机架|
|**supportedInstanceType**|String[]|专有宿主机支持的云主机规格|
|**capacity**|[ResourceCapacity](#resourcecapacity)|专有宿主机资源使用信息|
|**instanceIds**|String[]|专有宿主机上的云主机ID|
|**charge**|[Charge](#charge)|计费信息|
|**createTime**|String|创建时间|
### <div id="Charge">Charge</div>
|名称|类型|描述|
|---|---|---|
|**chargeMode**|String|支付模式，取值为：prepaid_by_duration，postpaid_by_usage或postpaid_by_duration，prepaid_by_duration表示预付费，postpaid_by_usage表示按用量后付费，postpaid_by_duration表示按配置后付费，默认为postpaid_by_duration|
|**chargeStatus**|String|费用支付状态，取值为：normal、overdue、arrear，normal表示正常，overdue表示已到期，arrear表示欠费|
|**chargeStartTime**|String|计费开始时间，遵循ISO8601标准，使用UTC时间，格式为：YYYY-MM-DDTHH:mm:ssZ|
|**chargeExpiredTime**|String|过期时间，预付费资源的到期时间，遵循ISO8601标准，使用UTC时间，格式为：YYYY-MM-DDTHH:mm:ssZ，后付费资源此字段内容为空|
|**chargeRetireTime**|String|预期释放时间，资源的预期释放时间，预付费/后付费资源均有此值，遵循ISO8601标准，使用UTC时间，格式为：YYYY-MM-DDTHH:mm:ssZ|
### <div id="ResourceCapacity">ResourceCapacity</div>
|名称|类型|描述|
|---|---|---|
|**totalVCPUs**|Integer|专有宿主机总VCPU数|
|**totalMemoryMB**|Integer|专有宿主机总内存大小，单位MB|
|**totalDiskGB**|Integer|专有宿主机总本地磁盘大小，单位GB|
|**totalGPUs**|Integer|专有宿主机总GPU个数|
|**usedVCPUs**|Integer|专有宿主机已分配的VCPU数|
|**usedMemoryMB**|Integer|专有宿主机已分配的内存大小，单位MB|
|**usedDiskGB**|Integer|专有宿主机已分配的本地磁盘大小，单位GB|
|**usedGPUs**|Integer|专有宿主机已分配的GPU个数|
|**localDiskType**|String|专有宿主机本地盘类型|
|**instanceCount**|Integer|专有宿主机上的云主机个数|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
|**400**|Invalid parameter|
|**401**|Authentication failed|
|**404**|Not found|
|**500**|Internal server error|
|**503**|Service unavailable|
