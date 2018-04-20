---
layout: default
id: state_alldev_realdata
title: 某项目所有设备当前实时数据
prev: project_alarmconfig.html
next: state_dev_realdata.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/realdata/get?AccessToken=ACCESSTOKEN

#### 请求方法
> POST

#### Content-Type
> application/x-www-form-urlencoded

### 请求参数
| 参数名称        | 说明           | 类型  |   是否必须  |
| ------------- |:-------------:|:------:|-----:|
| ProjectCode      | 项目编号 | String |  是   |


### 返回参数
| 参数名称        | 说明           | 类型  |
| ------------- |:-------------:| -----:|
| DeviceID      | 设备编号 | String |
| DataCode        | 参数编号 | String |
| CollectTime      | 采集时间      | String |
| CollectData      | 参数值 | String |

### 成功返回JSON示例
```
{
    "state"：0,
    "ProjectCode":"1",
    "data":[{
            "DeviceID":"1",
            "DataCode":"1",
            "CollectTime":"2016-03-01 05:00",
            "CollectData":"4702"
        },
        {
            "DeviceID":"2",
            "DataCode":"1",
            "CollectTime":"2016-03-01 05:00",
            "CollectData":"472"
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
