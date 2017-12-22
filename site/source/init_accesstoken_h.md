---
layout: default
id: init_accesstoken_h
title: 获取 access token(2)
next: init_accesstoken.html
---

### 说明
> 所有请求 **EFOS API** 接口的请求均使用此规则校验

### 请求头规则
每次请求 **EFOS API** 接口时，均需要提供 **4** 个 **HTTP Request Header**，具体如下：  

| 参数名称        | 说明                      | 类型  |   是否必须  |
| ------------- |:-----------------------:|:-------------:|-----:|
| AppyKey  | 开发者平台分配的 App Key | String |  是   |
| Nonce    | 随机数，无长度限制 | String |  是   |
| Timestamp   | 时间戳，从 1970 年 1 月 1 日 0 点 0 分 0 秒开始到现在的秒数 | String |  是   |
| Signature   | 数据签名 | String |  是   |

### Signature 生成规则
将系统分配的 AppSecret、Nonce (随机数)、Timestamp (时间戳)三个字符串按先后顺序拼接成一个字符串并进行 SHA1 哈希计算。如果调用的数据签名验证失败，接口调用会返回 HTTP 状态码 401。其他状态码请参见状态码表。

javascript 伪代码如下:
```javascript
// 开发者平台分配的 AppSecret
const appSecret = 'djias8834ndaslamsdf882dfas'; 
// 获取随机数
const nonce = GenerateRandNumber(); 
// 获取时间戳
const timestamp = new Date.getTime(); // 获取时间戳。
// 拼接字符串进行加密
let signature = sha1(appSecret + "_" + nonce + "_" + timestamp);

/**
* @return { Number } 随机数
*/
function GenerateRandNumber(){
    // 在这里定义随机数生成规则
}
```

请求参数示例
```
POST /realdata/get HTTP/1.1
Host: webapi.eegrid.com
AppKey: dfsf343123asds
Nonce: 344542434
Timestamp: 1513928026453
Signature: 1jd7s7cc7djaud9a8e711219a438fu74a5b0189d
Content-Type: application/x-www-form-urlencoded
Content-Length: 332

ProjectCode=7&DeviceID=123
```

### 返回码说明
| 返回码        | 说明           |
| ------------- | -------------:|
| 1      | 系统繁忙，此时请开发者稍候再试 |
| 0      | 请求成功      | 
| 40001      | 验证失败 |