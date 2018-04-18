---
layout: default
id: project_devicetype
title: 项目下所有设备类型
prev: project_device_system.html
next: project_device.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/devicetype/get?accessToken=ACCESSTOKEN

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
| DeviceTypeID      | 设备类型编号 | String |
| ParentCode      | 父级设备类型编号      | String |
| DeviceTypeName      | 设备类型名称      | String |
| SystemCode      | 所属设备系统      | String |


### 成功返回JSON示例
```
{
    "State"：0,
    "ProjectCode":1,
    "Data": [
        {
            "DeviceTypeID":1,
            "ParentCode":null,
            "DeviceTypeName":"高压开关柜",
            "SystemCode":1
        },
        {
            "DeviceTypeID":2, 
            "ParentCode":1,
            "DevieceTypeName":"高压进线柜",
            "SystemCode":1
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


