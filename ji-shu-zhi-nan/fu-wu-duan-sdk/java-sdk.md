# Java SDK

## 说明

用于java服务端数据上报，一般上报服务端的支付数据

[数据上报规范](../shu-ju-shang-bao-gui-fan.md)



## SDK下载地址

(http://xxxx.lizhifm.com/xxxx.jar)



## 使用示例

```java
import common_datasdk.model.PayEvent;

public class HttpDataSdkTest {
	
    private final static String serverUrl = "http://logmarket.lizhifm.com/collect_sa";
    public final static CommonDataSdk dataSdk = new CommonDataSdkImpl(new HttpConsumer(serverUrl));
	
    @Test
    public void testSendPay() throws Exception {

        PayEvent payEvent = new PayEvent();
        payEvent.setProduct_id(""); //应用ID，后台分配
        payEvent.setEventTime(System.currentTimeMillis());
        payEvent.setOrderId("order_01"); //支付定单ID，排重使用
        payEvent.setAmount(100 * 10L); //金额,单位:分
        payEvent.setApp_device_id("test_device_id"); //设备ID
        payEvent.setLogin_id("test_user_id"); //用户ID
        
        for(int i = 0; i < 100; i++) {
        	dataSdk.track("distinctId", payEvent);
        }
        
        dataSdk.flush(); //强制flush 发送数据,可以不用调用
    }
}
```

