# describeTde


## 描述
查看当前实例是否开启TDE

## 请求方式
GET

## 请求地址
https://rds.jdcloud-api.com/v1/regions/{regionId}/instances/{instanceId}/tde

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域代码，取值范围参见[《各地域及可用区对照表》](../Enum-Definitions/Regions-AZ.md)|
|**instanceId**|String|True| |RDS 实例ID，唯一标识一个RDS实例|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](describetde#result)| |

### <div id="result">Result</div>
|名称|类型|描述|
|---|---|---|
|**status**|String|当前实例是否已经开启TDE功能，如已开启，返回true；如未开启，返回false；开启中，返回pending|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|

## 请求示例
GET
```
public void testDescribeTde() {
    DescribeTdeRequest request = new DescribeTdeRequest();
    request.setInstanceId("sqlserver-83uqv7avy4");
    request.setRegionId("cn-north-1");
    DescribeTdeResponse response = rdsClient.describeTde(request);
    System.out.println(new Gson().toJson(response));
}

```

## 返回示例
```
{
    "requestId": "bpaopha7ujj6nn4ikjm4vhuo6oom2ovd", 
    "result": {
        "status": "false"
    }
}
```
