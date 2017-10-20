---
layout: default
id: project_navparams
title: 项目房间(导航)与环境监测设备
prev: project_deviceparams.html
next: project_device_datacode.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/navparame/get?AccessToken=ACCESSTOKEN

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
| NavCode      | 导航编号 | String |
| NavName      | 导航名称      | String |
| ParamName      | 参数名称 | String |
| DeviceID      | 设备编号      | String |
| DataCode        | 参数编号 | String |

### 成功返回JSON示例
```
{
    State：0,
    ProjectCode:1,
    Data: [
        {
            NavCode:1,
            NavName:变压器房（主楼-2f）,
            ParamName:室温,
            DeviceID:4,
            DataCode:31
        },
        {
            NavCode:2,
            NavName:1#配电房（主楼-2F）,
            ParamName:室温,
            DeviceID:15,
            DataCode:32
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
