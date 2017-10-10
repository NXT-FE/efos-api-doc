---
layout: default
id: alarm_dataspan_data
title: 某项目当前设定周期内最新告警
prev: energy_dev_hourdata.html
next: alarm_day_historydata.html
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
| Cycle      | 周期[单位:分钟，如:10] | String |  是   |

### 返回参数
| 参数名称        | 说明           | 类型  |
| ------------- |:-------------:| -----:|
| AlarmID      | 告警编号 | String |
| AlarmLevel      | 报警等级（一般告警、重要告警），暂不不提供事件信息。      | String |
| AlarmType      | 报警类型（如：过温） | String |
| DeviceID      | 设备编号      | String |
| DataCode        | 参数编号 | String |
| CollectData      | 参数值 | String |
| Alarmtime      | 报警时间      | String |
| AlarmInfo        | 报警信息 | String |





### 成功返回JSON示例
```
{
    "State"：0,
    "ProjectCode":"1",
    "Data":[
        {
            "DeviceID":"1",
            "DataCode":"1",
            "CollectData":"70",
            "AlarmID":"23",
            "AlarmLevel":"一般告警",
            "AlarmType":"过温",
            "AlarmTime":" 2016-01-12 09:00",
            "AlarmInfo":"变压器温度过高"
        },
        {
            "DeviceID":"7",
            "DataCode":"41",
            "CollectData":"2093.14",
            "AlarmID":"75",
            "AlarmLevel": "严重告警",
            "AlarmType": "过流告警",
            "AlarmTime":"2016-01-12 09:03",
            "AlarmInfo":"过流告警,当前值:2093.14"
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
