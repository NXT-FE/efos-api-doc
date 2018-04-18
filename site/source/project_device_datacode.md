---
layout: default
id: project_device_datacode
title: 设备采集参数
prev: project_navparams.html
next: project_alarmconfig.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/datamapping/get?accessToken=ACCESSTOKEN

#### 请求方法
> POST

#### Content-Type
> application/x-www-form-urlencoded

### 请求参数
| 参数名称        | 说明           | 类型  |   是否必须  |
| ------------- |:-------------:|:------:|-----:|
| ProjectCode   | 项目编号 | String |  是   |

### 返回参数
| 参数名称        | 说明           | 类型  |
| ------------- |:-------------:| -----:|
| DeviceID      | 设备编号 | String |
| DeviceName    | 设备名称      | String |
| DataCode      | 数据标识编号     | String |
| DataName      | 数据标识名称      | String |

### 成功返回JSON示例
```
{
    "State"：0,
    "ProjectCode":"1",
    "Data": [
        {
            "DeviceID": 1,
            "DeviceName": "1#进线1",
            "DataCode": 44,
            "DataName": "A相电压"
        },
        {
            "DeviceID": 1,
            "DeviceName": "1#进线1",
            "DataCode": 46,
            "DataName": "C相电压"
        }
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

