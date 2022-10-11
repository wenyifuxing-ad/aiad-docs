# 苹果IOS SDK

IOS 采用神策SDK上报数据。

\[神策SDK 上报文档]\([https://manual.sensorsdata.cn/sa/latest/sdk-ios-7538614.html](https://manual.sensorsdata.cn/sa/latest/sdk-ios-7538614.html))



\#设置公共属性

\##设备ID

\[\[SensorsAnalyticsSDK sharedInstance] registerSuperProperties:@{@"app\_device\_id" : @"SOME DEVICE ID"}];

\##苹果IDFA

\[\[SensorsAnalyticsSDK sharedInstance] registerSuperProperties:@{@"idfa" : @""}];

\##用户浏览器UserAgent

\[\[SensorsAnalyticsSDK sharedInstance] registerSuperProperties:@{@"attribute\_ua" : @""}];





\#上报事件

(\`UInt64 productId = 123456; NSString \*productCatalog = @"Laptop Computer"; BOOL isAddedToFavorites = NO;

\[\[SensorsAnalyticsSDK sharedInstance] track:@"BuyProduct" withProperties:@{@"ProductID" : \[NSNumber numberWithUnsignedLong:productId], @"ProductCatalog" : productCatalog, @"IsAddedToFav" : @(isAddedToFavorites)}];

\`)

