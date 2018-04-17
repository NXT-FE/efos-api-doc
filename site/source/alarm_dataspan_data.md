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
| Cycle      | 周期[单位:分钟，如:10] | String |  否   |

### 返回参数
| 参数名称        | 说明           | 类型  |
| ------------- |:-------------:| -----:|
| AlarmID      | 告警编号 | String |
| AlarmLevel      | 报警等级（[1:事件，2:一般告警，3:严重告警]），暂不不提供事件信息。      | String |
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
            "DeviceID":"61",
            "DataCode":"1010",
            "CollectData":"0.31",
            "AlarmID":"32341",
            "AlarmLevel":"一般告警",
            "AlarmType":"压力低压告警",
            "AlarmTime":" 2016-01-12 09:00",
            "AlarmInfo":"消防泵房_喷淋泵压力表-压力低压告警当前值:0.31 Mpa"
        },
        {
            "DeviceID":"7",
            "DataCode":"41",
            "CollectData":"1040.0",
            "AlarmID":"21125",
            "AlarmLevel": "严重告警",
            "AlarmType": "故障告警",
            "AlarmTime":"2016-01-12 09:03",
            "AlarmInfo":" A座-3楼弱电井_ 3APJ1 电箱-故障告警当前值:1040.0 mA"
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
