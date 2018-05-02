---
layout: default
id: alarm_group
title: 某集团所有实时告警
prev: alarm_day_alldev_historydata.html
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

无

### 返回参数

| 参数名称    |                                说明                                |   类型 |
| ----------- | :----------------------------------------------------------------: | -----: |
| ProjectCode |                              项目编号                              | String |
| ProjectName |                              项目名称                              | String |
| DeviceID    |                              设备编号                              | String |
| DataCode    |                              参数编号                              | String |
| CollectData |                               参数值                               | String |
| AlarmID     |                              告警编号                              | String |
| AlarmLevel  | 报警等级（[1:事件，2:一般告警，3:严重告警]），暂不不提供事件信息。 | String |
| AlarmType   |                        报警类型（如：过温）                        | String |
| Alarmtime   |                              报警时间                              | String |
| AlarmInfo   |                              报警信息                              | String |
| NavName     |                              设备位置                              | String |
| DeviceName  |                              设备名称                              | String |
| AlarmDetail |                              告警详细                              | String |

### 成功返回 JSON 示例

```
{
    "state":"0",
    "data":[
        {
            "ProjectCode": 1,
            "ProjectName": "测试项目1",
            "DeviceID":"61",
            "DataCode":"1010",
            "CollectData":"0.31",
            "AlarmID":"32341",
            "AlarmLevel":"一般告警",
            "AlarmType":"压力低压告警",
            "AlarmTime":" 2016-01-12 09:00",
            "AlarmInfo":"消防泵房_喷淋泵压力表-压力低压告警当前值:0.31 Mpa",
            "NavName":"消防泵房",
            "DeviceName":"喷淋泵压力表",
            "AlarmDetail":"压力低压告警当前值:0.31 Mpa"
        },
        {
            "ProjectCode": 2,
            "ProjectName": "测试项目2",
            "DeviceID": "1",
            "DataCode": "41",
            "CollectData": "1.0",
            "AlarmID":"21131",
            "AlarmLevel":" 严重告警",
            "AlarmType":" 故障告警",
            "AlarmTime":"2016-01-12 09:20",
            "AlarmInfo":" 1层风机_AHU-WG-1 (25)-故障告警当前值:1.0",
            "NavName":"1层风机",
            "DeviceName":"AHU-WG-1 (25)",
            "AlarmDetail":"故障告警当前值:1.0"
        },
    …
    ]
}
```

### 失败返回 JSON 示例

```
{
    "state": -1,
    "errorMessage": "此处显示失败信息"
}
```
