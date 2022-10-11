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
        payEvent.setProduct_id("9999901");
        payEvent.setEventTime(System.currentTimeMillis());
        payEvent.setOrderId(""+System.currentTimeMillis());
        payEvent.setAmount(100 * 10);
        payEvent.setAppDeviceId("test_device_id");
        payEvent.setUserId("test_user_id");
        
        for(int i = 0; i < 100; i++) {
        	dataSdk.track("some_distinctId", payEvent);
        	dataSdk.flush();
        }
        
    }
}
```

