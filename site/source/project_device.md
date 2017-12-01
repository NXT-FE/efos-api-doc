---
layout: default
id: project_device
title: 项目下所有设备
prev: project_devicetype.html
next: project_deviceparams.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/device/get?AccessToken=ACCESSTOKEN

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
| TypeID        | 设备类型编号 | String |
| TypeName      | 设备类型      | String |
| NavName       | 位置      | String |
| DeviceID      | 设备编号      | String |
| DeviceCode    | 客户设备标准编码      | String |
| DeviceName    | 设备名称      | String |
| IsDisplay     | 是否显示(为 true 则表示真实设备，false 则表示虚拟设备)      | Boolean |


### 成功返回JSON示例
```
{
    "State"：0,
    "ProjectCode":1,
    "Data": [
        {
            "TypeID":1,
            "TypeName":"变压器"
            "NavName":"配电房",
            "DeviceCode":"WD-SW-1023",
            "DeviceID":1,
            "DeviceName":"1#变压器",
            "IsDisplay":true
            
        },
        {
            "TypeID":9101,
            "TypeName":"温湿度", 
            "NavName": "生活泵房",
            "DeviceCode":"WD-SW-1024",
            "DeviceID":2,		
            "DeviceName":"生活水泵房温湿度",
            "IsDisplay":false
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

