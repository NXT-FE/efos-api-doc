---
layout: default
id: project_deviceparams
title: 项目下所有设备参数
prev: project_device.html
next: project_navparams.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/deviceparame/get?AccessToken=ACCESSTOKEN

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
| DataCode      | 参数编号 | String |
| DataName      | 参数名称      | String |
| Unit      | 单位      | String |


### 成功返回JSON示例
```
{
    "state"：0,
    "ProjectCode":1,
    "data": [
        {
            "DataCode":1,
            "DataName":"电压",
            "Unit":"V"
        },
        {
            "DataCode":2,
            "DataName":"电流",
            "Unit":"A"
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
