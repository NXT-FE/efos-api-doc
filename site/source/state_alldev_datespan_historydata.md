---
layout: default
id: state_alldev_datespan_historydata
title: 某项目某时间段所有设备历史数据
prev: state_dev_day_hourdata.html
next: energy_alldev_daydata.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/historydataspan/get?AccessToken=ACCESSTOKEN

#### 请求方法
> POST

#### Content-Type
> application/x-www-form-urlencoded

### 请求参数
| 参数名称        | 说明           | 类型  |   是否必须  |
| ------------- |:-------------:|:------:|-----:|
| ProjectCode      | 项目编号 | String |  是   |
| StartTime      | 开始时间( 2016-12-12 10:22  ) | String |  是   |
| EndTime      | 结束时间(2016-12-12  22:22  ) | String |  是   |

### 返回参数
| 参数名称        | 说明           | 类型  |
| ------------- |:-------------:| -----:|
| DeviceID      | 设备编号 | String |
| DataCode        | 参数编号 | String |
| CollectTime      | 采集时间      | String |
| CollectData      | 参数值 | String |

> 注：请求不可跨天( StartTime \ EndTime 必须为同一天 )

### 成功返回JSON示例
```
{
    "state"：0,
    "ProjectCode":1,
    "data": [
        {
            "NavCode":1,
            "NavName":"变压器房（主楼-2f）",
            "ParamName":"室温",
            "DeviceID":4,
            "DataCode":31
        },
        {
            "NavCode":2,
            "NavName":"1#配电房（主楼-2F）",
            "ParamName":"室温",
            "DeviceID":15,
            "DataCode":32
        }
    ]
}


```

### 失败返回JSON示例 
```
{
    "state": -1,
    "errorMessage": "此处显示失败信息"
}
```
