---
layout: default
id: project_device_system
title: 设备系统信息
prev: project_alarmtype.html
next: project_devicetype.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/devicesystem/get?AccessToken=ACCESSTOKEN

#### 请求方法
> POST

#### Content-Type
> application/x-www-form-urlencoded

### 请求参数
> 无

### 返回参数
| 参数名称        | 说明           | 类型  |
| ------------- |:-------------:| -----:|
| SystemCode    | 系统编号 | String |
| SystemName    | 系统名称   | String |


### 成功返回JSON示例
```
{
    "State"：0,
    "Data": [
        {
            "SystemCode":1,
            "SystemName":"供配电系统"
        },
        {
            "SystemCode":2,
            "SystemName":"给排水系统"
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

