---
layout: default
id: state_dev_historydata
title: 某项目某一时刻某设备历史数据
pre: state_alldev_historydata.html
next: state_dev_day_hourdata.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/historydata/get?AccessToken=ACCESSTOKEN

#### 请求方法
> POST

#### Content-Type
> application/x-www-form-urlencoded

### 请求参数
| 参数名称        | 说明           | 类型  |   是否必须  |
| ------------- |:-------------:|:------:|-----:|
| ProjectCode      | 项目编号 | String |  是   |
| DeviceID      | 设备编号 | String |  是   |
| Date      | 时刻，如(2016-1-12 10:00) | String |  否，默认当前时刻   |

### 返回参数
| 参数名称        | 说明           | 类型  |
| ------------- |:-------------:| -----:|
| DeviceID      | 设备编号 | String |
| DataCode        | 参数编号 | String |
| CollectTime      | 采集时间      | String |
| CollectData      | 参数值 | String |

> 注：返回离该时刻最近有数据时刻的数据

### 成功返回JSON示例
```
{
    "State"：0,
    "ProjectCode":"1",
    "Data":[{
        "DeviceID":1,
        "DataCode":"1",
        "CollectTime":"2016-01-12 05:00",
        "CollectData":"4702"
    },
    {
        "DeviceID":1,
        "DataCode":"2",
        "CollectTime":"2016-01-12 05:00",
        "CollectData":"472"
    }
    …
    ]
}



```

### 失败返回JSON示例 
```
{
    "State": -1,
    "ErrorMessage": "此处显示失败信息"
}
```
