---
layout: default
id: init_accesstoken
title: 获取 access token
next: init_accesstoken.html
---

### 请求
access_token是 EFOS API 的全局唯一接口调用凭据，公众号调用各接口时都需使用access_token。开发者需要进行妥善保存。
access_token的存储至少要保留512个字符空间。access_token的有效期目前为24个小时，需定时刷新，
重复获取将导致上次获取的access_token失效。

#### 地址
> https://webapi.eegrid.com/efos-api/token?grant_type=client_credential&appid=APPID&secret=APPSECRET

#### 请求方法
> GET

### 请求参数
| 参数名称        | 说明           | 类型  |   是否必须  |
| ------------- |:-------------:|:------:|-----:|
| grant_type    | 获取access_token填写client_credential | String |  是   |
| appid       | 第三方用户唯一凭证 | String |  是   |
| secret      | 第三方用户唯一凭证密钥，即appsecret | String |  是   |



### 返回参数
| 参数名称        | 说明           | 类型  |
| ------------- |:-------------:| -----:|
| access_token      | 获取到的凭证 | String |
| expires_in      | 凭证有效时间，单位：秒      | String |

ps:**台会保证过期后5分钟内，新老access_token都可用，保证业务的平滑过渡**



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
    "errcode":40013,
    "errmsg":"invalid appid"
}
```

### 返回码说明
| 返回码        | 说明           |
| ------------- | -------------:|
| 1      | 系统繁忙，此时请开发者稍候再试 |
| 0      | 请求成功      | 
| 40001      | AppSecret 错误或者 AppSecret 不存在，请开发者确认AppSecret的正确性 |
| 40002      | 请确保grant_type字段值为client_credential      | 
| 40164      | 调用接口的IP地址不在白名单中，请在接口IP白名单中进行设置      | 