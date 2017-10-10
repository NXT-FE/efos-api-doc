---
layout: default
id: efos_h5_page
title: EFOS H5 接口说明
prev: other_ps.html
---

### 请求
#### 地址
> http://webapi.eegrid.com/app/deviceindex.html?accesstoken=ACCESSTOKEN&projectcode=ProjectCode

#### 请求方法
> GET


### 参数
| 参数名称        | 说明           | 类型  |   是否必须  |
| ------------- |:-------------:|:------:|-----:|
| accesstoken      | 请求票据 | String |  是   |
| projectcode      | 项目编号 | String |  是   |


### 成功返回示例
以访问 **XXX** 项目为例:    
    
成功返回结果即为 **XXX** 设施详情首页  
![](http://osv2a938x.bkt.clouddn.com/efos_h5_succeed.png)


### 失败返回示例
若 **accesstoken** 不正确或者 **projectcode** 不存在，则会返回下述页面:  
![](http://osv2a938x.bkt.clouddn.com/efos_h5_failed.png)

