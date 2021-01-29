#                                         creditScore

## 服务描述

获取数据风险等级和标签

## 请求方式

POST

## 请求地址

https://bri.jdcloud-api.com/v1/creditScore:check


## 请求参数

| 名称      | 类型       | 是否必需 | 默认值 | 描述                                                         |
| --------- | ---------- | -------- | ------ | ------------------------------------------------------------ |
| **tasks** | CreditTask | True     |        | 检测任务列表，包含一个或多个元素。每个元素是个结构体，最多可添加100元素，即最多对100个数据进行评分。每个元素的具体结构描述见creditTask。 |

### <div id="CreditTask">CreditTask</div>

| 名称             | 类型   | 是否必需 | 默认值 | 描述                                       |
| ---------------- | ------ | -------- | ------ | ------------------------------------------ |
| **dataId**       | String | False    |        | 数据Id。需要保证在一次请求中所有的Id不重复 |
| **content**      | String | True     |        | 待检测数据，最长512个字符                  |
| **resourceType** | String | True     |        | 数据类型，ip-IP，phone-手机，addr-地址     |

## 返回参数

| 名称       | 类型   | 描述                              |
| ---------- | ------ | --------------------------------- |
| **result** | Result | API请求成功或者部分成功时返回数据 |

### <div id="Result">Result</div>

| 名称     | 类型         | 描述     |
| -------- | ------------ | -------- |
| **data** | CreditResult | 结果数组 |

### <div id="CreditResult">CreditResult</div>

| 名称             | 类型              | 描述                                                         |
| ---------------- | ----------------- | ------------------------------------------------------------ |
| **success**      | Boolean           | 是否成功，没成功会在failMsg附上错误信息                      |
| **failMsg**      | String            | 错误描述信息                                                 |
| **dataId**       | String            | 对应请求的dataId                                             |
| **inBWList**     | String            | 是否命中黑白名单，black-在黑名单中 white-在白名单中 none-不在任何名单中 |
| **content**      | String            | 对应请求的内容                                               |
| **resourceType** | String            | 数据类型，ip-IP，phone-手机，addr-地址                       |
| **scoreDetail**  | CreditScoreDetail | 评分数据                                                     |

### <div id="CreditScoreDetail">CreditScoreDetail</div>

| 名称          | 类型   | 描述                                                         |
| ------------- | ------ | ------------------------------------------------------------ |
| **riskTag**   | String | 风险类型，对应riskCode的中文描述                             |
| **riskCode**  | String | 风险类型编码，对应riskCode的分类：<br/>201-207手机综合风险，包括201-异常注册、202-异常登录、203-营销刷券、204-下单黄牛、205-异常支付、206-恶意售后、207-猫池小号<br>501-507IP综合风险，包括501-普通代理、 502-秒拨代理IP、503-真人作弊、504-设备伪装、505-地址伪装、506-黑软IP、507-爬虫IP |
| **riskClass** | String | 风险分类，包括ip、phone、addr                                |
| **score**     | String | 风险评分，1-低风险 2-中低风险 3-中风险 4-中高风险 5-高风险 0-未知 |
| **scoreDesc** | String | 对应score的中文描述，1-低风险 2-中低风险 3-中风险 4-中高风险 5-高风险 0-未知 |

## 返回码

| 返回码  | 描述        |
| ------- | ----------- |
| **200** | OK          |
| **400** | Bad Request |

## 示例代码

```
请求：
method：
  post
body：
{
  "tasks": [
    {
      "content": "116.196.12.23",
      "resourceType": "ip"
    },
    {
      "content": "15901668899",
      "resourceType": "phone"
    },
    {
      "content": "北京市朝阳区北辰西路8号",
      "resourceType": "addr"
    }
  ]
}

返回:
{
  "requestId": "1",
  "result": {
    "data": [
      {
        "success": true,
        "failMsg": "",
        "dataId": "test",
        "content": "116.196.12.23",
        "resourceType": "ip",
        "scoreDetail": {
          "riskTag": "黑软IP",
          "riskCode": "506",
          "riskClass": "ip",
          "score": "3",
          "scoreDesc": "中风险"
        },
        "hitCache": "miss",
        "inBWList": "none"
      },
      {
        "success": true,
        "failMsg": "",
        "dataId": "test",
        "content": "15901668899",
        "resourceType": "phone",
        "scoreDetail": {
          "riskTag": "异常注册风险",
          "riskCode": "202",
          "riskClass": "phone",
          "score": "4",
          "scoreDesc": "中高风险"
        },
        "hitCache": "miss",
        "inBWList": "none"
      },
      {
        "success": true,
        "failMsg": "",
        "dataId": "test",
        "content": "北京市朝阳区北辰西路8号",
        "resourceType": "addr",
        "scoreDetail": {
          "riskTag": "none",
          "riskCode": "none",
          "riskClass": "addr",
          "score": "1",
          "scoreDesc": "低风险"
        },
        "hitCache": "miss",
        "inBWList": "none"
      }
    ]
  }
}
```
