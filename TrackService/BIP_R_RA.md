# 轨迹推送注册

## 接口说明
```java
    /**
     * 轨迹推送注册
     * @param eventTag 注册事件类型，轨迹实时推送填：real_time_trace
     * @param callBackUrl 数据推送的回调地址
     * @return java.lang.String
     **/
    String BipRegisterRegisterApp(String eventTag, String callBackUrl);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2531)
## 实现方法
```java
    /**
     * 轨迹推送注册
     * @param eventTag 注册事件类型，轨迹实时推送填：real_time_trace
     * @param callBackUrl 数据推送的回调地址
     * @return java.lang.String
     **/
    @Override
    public String BipRegisterRegisterApp(String eventTag, String callBackUrl) {
        PostClient postClient = this.newGadPostClient(GadTraceConstants.BIP_REGISTER_REGISTER_APP)
                .addParameter("eventTag", eventTag)
                .addParameter("callBackUrl", callBackUrl);
        return postClient.post();
    }
```