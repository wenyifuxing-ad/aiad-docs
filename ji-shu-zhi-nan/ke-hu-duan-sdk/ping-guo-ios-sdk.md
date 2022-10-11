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

[[SensorsAnalyticsSDK sharedInstance] track:@"BuyProduct"
							 withProperties:@{@"ProductID" : [NSNumber numberWithUnsignedLong:productId],
											  @"ProductCatalog" : productCatalog,
```



### 上报ASA苹果信息

事件ID： EVENT\_MARKET\_DOWNLOAD\_STORE\_RESULT

#### 事件属性:

asa\_info: 字符串，苹果asa返回归因json信息，分IOS14.3之前和14.3以后

#### [如何获得ASA信息](https://juejin.cn/post/6978116612326948894)



