---
layout: default
id: init_accesstoken
title: 获取 access token
next: init_accesstoken_h.html
---

### 请求
**access_token** 是 **EFOS API** 的全局唯一接口调用凭据，调用 **EFOS** 各接口时都需使用 **access_token**。开发者需要进行妥善保存。
**access_token** 的存储至少要保留 **512** 个字符空间。**access_token** 的有效期目前为 **24** 个小时，需定时刷新，
重复获取将导致上次获取的 **access_token** 失效。  


#### 地址
> https://webapi.eegrid.com/efos-api/token?grant_type=client_credential&appid=APPID&secret=APPSECRET

#### 请求方法
> GET

### 请求参数
| 参数名称        | 说明           | 类型  |   是否必须  |
| ------------- |:-------------:|:------:|-----:|
| grant_type  | 获取 access_token 填写 client_credential | String |  是   |
| AppKey       | 第三方用户唯一凭证 | String |  是   |
| AppSecret      | 第三方用户唯一凭证密钥 AppSecret | String |  是   |



### 返回参数
| 参数名称        | 说明           | 类型  |
| ------------- |:-------------:| -----:|
| access_token      | 获取到的凭证 | String |
| expires_in      | 凭证有效时间，单位：秒      | String |

ps:**后台会保证过期后5分钟内，新老 access_token 都可用，保证业务的平滑过渡**



### 成功返回JSON示例
```
{
    "access_token":"ACCESS_TOKEN",
    "expires_in":7200
}
```

### 失败返回JSON示例 
```
{
    "errcode":40001,
    "errmsg":"invalid appid"
}
```

### 返回码说明
| 返回码        | 说明           |
| ------------- | -------------:|
| 1      | 系统繁忙，此时请开发者稍候再试 |
| 0      | 请求成功      | 
| 40001      | invalid appid |
| 40002      | AppSecret 错误，请确认AppSecret的正确性 |
| 40003      | 请确保 grant_type 字段值为 client_credential      | 