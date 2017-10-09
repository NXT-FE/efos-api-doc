---
layout: default
id: project_deviceparams
title: 项目下所有设备参数
pre: project_device.html
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


### 成功返回JSON示例
```
{
    State：0,
    ProjectCode:1,
    Data: [
        {
            DataCode:1,
            DataName:参数1
        },
        {
            DataCode:2,
            DataName:参数2
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
