---
layout: default
id: project_auth
title: 项目权限
next: project_alarmtype.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/project/get?AccessToken=ACCESSTOKEN

#### 请求方法
> POST

### 返回参数
| 参数名称        | 说明           | 类型  |
| ------------- |:-------------:| -----:|
| ProjectCode      | 项目编号 | String |
| ProjectName      | 项目名称      | String |
| Area      | 项目面积（单位: ㎡）      | String |



### 成功返回JSON示例
```
{
    "state"：0,
    "data": [
        {
            "ProjectCode":"1",
            "ProjectName":"项目1",
            "Area":"71450"
        },
        {
            "ProjectCode":"2",
            "ProjectName":"项目2",
            "Area":"82441"
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
