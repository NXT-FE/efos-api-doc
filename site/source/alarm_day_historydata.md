---
layout: default
id: alarm_day_historydata
title: 某项目某日所有历史告警
prev: alarm_dataspan_data.html
next: other_returncode.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/alarm/get?AccessToken=ACCESSTOKEN

#### 请求方法
> POST

#### Content-Type
> application/x-www-form-urlencoded

### 请求参数
| 参数名称        | 说明           | 类型  |   是否必须  |
| ------------- |:-------------:|:------:|-----:|
| ProjectCode      | 项目编号 | String |  是   |
| DeviceID      | 设备编号 | String |  是   |
| Date      | 时刻，如(2016-1-12 10:00) | String |  否，默认当天   |


### 返回参数
| 参数名称        | 说明           | 类型  |
| ------------- |:-------------:| -----:|
| DeviceID      | 设备编号      | String |
| DataCode        | 参数编号 | String |
| CollectData      | 参数值 | String |
| AlarmID      | 告警编号 | String |
| AlarmLevel      | 报警等级（一般告警、重要告警），暂不不提供事件信息。      | String |
| AlarmType      | 报警类型（如：过温） | String |
| Alarmtime      | 报警时间      | String |
| AlarmInfo        | 报警信息 | String |

### 成功返回JSON示例
```
{
    "State":"0",
    "ProjectCode":"1",
    "Data":[
        {
            "DeviceID":"1",
            "DataCode":"1",
            "CollectData":" 70",
            "AlarmID":"23",
            "AlarmLevel":"一般告警",
            "AlarmType":" 过温告警",
            "AlarmTime":"2016-01-12 09:00",
            "AlarmInfo":"变压器温度过高"
        },
        {
            "DeviceID": "73",
            "DataCode": "41",
            "CollectData": "2099",
            "AlarmID":"23",
            "AlarmLevel":" 严重告警",
            "AlarmType":" 过流告警",
            "AlarmTime":"2016-01-12 09:20",
            "AlarmInfo":" 过流告警,当前值: 2099"
        },
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
