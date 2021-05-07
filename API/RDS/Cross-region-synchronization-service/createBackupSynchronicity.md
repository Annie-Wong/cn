# createBackupSynchronicity


## 描述
创建一个跨地域备份同步服务。

## 请求方式
POST

## 请求地址
https://rds.jdcloud-api.com/v1/regions/{regionId}/backupSynchronicities

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域代码，取值范围参见[《各地域及可用区对照表》](../Enum-Definitions/Regions-AZ.md)|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**instanceId**|String|True| |源实例ID|
|**destRegion**|String|True| |备份同步的目标地域|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](createbackupsynchronicity#result)| |

### <div id="result">Result</div>
|名称|类型|描述|
|---|---|---|
|**serviceId**|String|跨地域备份同步服务ID|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|

## 请求示例
POST
```
public void testCreateBackupSynchronicity() {
    CreateBackupSynchronicityRequest request = new CreateBackupSynchronicityRequest();
    request.setDestRegion("cn-east-2");
    request.setInstanceId("mysql-wp4e9ztap2");
    request.setRegionId("cn-north-1");
    CreateBackupSynchronicityResponse response = rdsClient.createBackupSynchronicity(request);
    System.out.println(new Gson().toJson(response));
}

```

## 返回示例
```
{
    "requestId": "bpa344ech6367jbt0tfeojpe578n61a9", 
    "result": {
        "serviceId": "dbs-r1q51ene3s5d"
    }
}
```
