---
layout: default
id: efos_pc_h5_page
title: EFOS PC H5 接口说明
prev: efos_app_h5_page.html
---

### 请求
#### 地址
> http://master.eegrid.com/PublishPage.aspx?projectCode=ProjectCode&funCode=FuncCode&accesstoken=ACCESSTOKEN

#### 请求方法
> GET


### 参数
| 参数名称        | 说明           | 类型  |   是否必须  |
| ------------- |:-------------:|:------:|-----:|
| accesstoken      | 请求票据 | String |  是   |
| projectcode      | 项目编号 | String |  是   |
| funCode      | 功能点编号 | String |  是   |

ps: **若为集团功能点，可以使用属于该集团下的任何一个项目的编号( projectcode )发起请求**

### 成功返回示例
以访问某集团综合态势页面为例，成功返回页面如下图所示:   
![](http://osv2a938x.bkt.clouddn.com/pc_h5_case.png)


### 失败返回示例
若 **accesstoken** 不正确或者 **projectcode** 或者  **funCode** 不存在，则会返回空白页提示:  
**没有该页面访问权限。**


