---
layout: default
id: energy_alldev_daydata
title: 某项目所有设备某日能耗
prev: state_alldev_datespan_historydata.html
next: energy_dev_hourdata.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/energy/get?accessToken=ACCESSTOKEN

#### 请求方法
> POST

#### Content-Type
> application/x-www-form-urlencoded

### 请求参数
| 参数名称        | 说明           | 类型  |   是否必须  |
| ------------- |:-------------:|:------:|-----:|
| ProjectCode      | 项目编号 | String |  是   |
| Date      | 日期，如(2016-1-12 00:00) | String |  否，默认当天   |

### 返回参数
| 参数名称        | 说明           | 类型  |
| ------------- |:-------------:| -----:|
| DeviceID      | 设备编号 | String |
| CollectTime      | 采集时间      | String |
| CollectData      | 参数值 | String（单位:kwh） |

> 注：请求不可跨天( StartTime \ EndTime 必须为同一天 )

### 成功返回JSON示例
```
{
    "state":"0",
    "ProjectCode":"1",
    "data":[
        {
            "DeviceID":"1",
            "CollectTime":"2016-01-29 23:00",
            "CollectData":" "321",
        },
        {
            "DeviceID":"2",
            "CollectTime":"2016-01-29 23:00",
            "CollectData":" "322",
        },
        …
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
