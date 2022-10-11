# 数据上报规范

## [客户端数据上报规范文档](https://lizhi2021.feishu.cn/sheets/shtcnqWySbGd8SHqOhlF0DZliJe?sheet=0cfdbf)





## 公共字段

| 字段名称            | 数据类型 | 描述                |
| --------------- | ---- | ----------------- |
| product\_id     | 字符串  | 必填，应用ID           |
| app\_device\_id | 字符串  | 设备ID              |
| androidId       | 字符串  | Android的androidId |
| oaId            | 字符串  | Android设备的OAID    |
| imei            | 字符串  | Android设备的IMEI    |
| macAddr         | 字符串  | mac地址             |
| attribute\_ua   | 字符串  | 用户浏览器的UserAgent   |
| login\_id       | 字符串  | 用户ID              |

## 服务端上报数据

### 上报支付数据

| 字段名称      | 数据类型 | 描述             | 示例值             |
| --------- | ---- | -------------- | --------------- |
| orderId   | 字符串  | 必填，定单ID，用于排重   | order\_dkdksdlk |
| amount    | 整数   | 必填，支付金额(单位: 分) | 100             |
| login\_id | 字符串  | 必填，用户ID        | user\_01        |





