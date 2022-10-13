# 苹果IOS SDK

## 使用介绍

IOS 采用神策SDK上报数据。

（[https://manual.sensorsdata.cn/sa/latest/sdk-ios-7538614.html](https://manual.sensorsdata.cn/sa/latest/sdk-ios-7538614.html)



具体上报事件，请查看 [数据上报规范](../shu-ju-shang-bao-gui-fan.md)





## 设置公共属性

### 设备ID

```
[[SensorsAnalyticsSDK sharedInstance] registerSuperProperties:@{@"app_device_id" : @"SOME DEVICE ID"}];
```

### 苹果IDFA

```
[[SensorsAnalyticsSDK sharedInstance] registerSuperProperties:@{@"idfa" : @""}];
```

### 用户浏览器UserAgent

```
[[SensorsAnalyticsSDK sharedInstance] registerSuperProperties:@{@"attribute_ua" : @""}];
```





## 上报事件

```objectivec
UInt64 productId = 123456;
NSString *productCatalog = @"Laptop Computer";
BOOL isAddedToFavorites = NO;

[[SensorsAnalyticsSDK sharedInstance] track:@"DemoBuyProduct"
							 withProperties:@{@"ProductID" : [NSNumber numberWithUnsignedLong:productId],
											  @"ProductCatalog" : productCatalog,
```



### 上报ASA苹果信息

事件ID： EVENT\_MARKET\_DOWNLOAD\_STORE\_RESULT

#### 事件属性:

asa\_info: 字符串，苹果asa返回归因json信息，分IOS14.3之前和14.3以后





#### 获取步骤描述：

1. 程序启动后调用ASA归因接口获取归因数据
2. 调用归因数据的接口以14.3为分界点，分别从iAd.framework与AdServices获取
3. 获取的数据通过数据SDK上报，获取的JSON需转为字符串



#### 相关文档：

#### [如何获得ASA信息](https://juejin.cn/post/6978116612326948894)

苹果官方文档： [https://developer.apple.com/documentation/iad/setting\_up\_apple\_search\_ads\_attribution#overview](https://developer.apple.com/documentation/iad/setting\_up\_apple\_search\_ads\_attribution#overview)



####

