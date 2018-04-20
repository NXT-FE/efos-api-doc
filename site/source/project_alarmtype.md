---
layout: default
id: project_alarmtype
title: 项目下所有告警类型
prev: project_auth.html
next: project_device_system.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/alarmtype/get?accessToken=ACCESSTOKEN

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
| TypeID      | 告警类型编号 | String |
| AlarmTypeName      | 告警类型名称      | String |
| AlarmTypeLevel      | 告警类型级别[1:事件，2:一般告警，3:严重告警]      | String |


### 成功返回JSON示例
```
{
    "state"：0,
    "ProjectCode":"1",
    "data": [
        {
            "TypeID":"1",
            "AlarmTypeName":"故障告警"
            "AlarmTypeLevel":"2"
        },
        {
            "TypeID":"2",
            "AlarmTypeName":"保护动作跳闸告警"
            "AlarmTypeLevel":"3"
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

