---
layout: default
id: intro
title: 简介
next: project_auth.html
---

**当前版本:1.5.5**
各集团用户请联系**商务人员**获取 **AccessToken**

## 修正项

### 1.5.5
* 修正部分请求字段与返回字段首字母未改为大写
* 告警类接口增加:设备位置 **NavName**、设备名称 **DeviceName**、告警详细 **AlarmDetail** 三个字段
* 增加某集团所有实时告警接口

### 1.5.4

* 新增 **设备采集参数** 接口
* 新增 **告警条件配置** 接口
* 新增 **某日某项目所有历史告警** 接口
* 新增 **EFOS PC H5 接口说明**
* 新增 **设备系统信息** 接口
* 项目下所有设备设备类型接口增加所属系统字段 **SystemCode**
* 项目下所有设备参数接口增加单位字段 **Unit**
* 增加告警配置接口 **Expression** 示例
* 告警条件配置接口增加告警级别字段 **AlarmLevel**
* 项目下所有设备接口增加客户设备标准编码字段 **DeviceCode**
* 项目下所有设备接口增加是否显示字段 **IsDisplay**
* 项目下告警条件配置接口增加告警类型编号字段 **AlarmTypeID**
* 项目权限接口增加面积字段 **Area**

### 1.5.3

* 新增 **项目下所有告警类型** 接口
* 新增 **项目下所有设备类型** 接口
* 项目下所有设备 接口新增 **NavCode(导航编码)** 字段
* 项目下所有设备 接口新增 **TypeID(设备类型编号)** 字段

#### 1.5.2

* 请求字段与返回字段首字母统一改为大写字母
* 去除返回参数中冗余的 **ProjectCode** 字段
