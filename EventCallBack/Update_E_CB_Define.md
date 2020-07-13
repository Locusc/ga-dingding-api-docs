# 更新事件回调的定义信息

## 接口说明
```java
    /**
     * 更新事件回调的定义信息
     * @param eventCallbackId 注册的回调id
     * @param callbackUrl 注册的http地址
     * @return java.lang.String
     **/
    String messageUpdateEventCallbackDefined(Long eventCallbackId, String callbackUrl);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2310)
## 实现方法
```java
    /**
     * 更新事件回调的定义信息
     * @param eventCallbackId eventCallbackId
     * @param callbackUrl callbackUrl
     * @return java.lang.String
     **/
    @Override
    public String messageUpdateEventCallbackDefined(Long eventCallbackId, String callbackUrl) {
        PostClient postClient = this.newGadPostClient(GadBECBApiConstants.MESSAGE_UPDATE_EVENT_CALLBACK_DEFINE);
        if(eventCallbackId != null) {
            postClient.addParameter("eventCallbackId", String.valueOf(eventCallbackId));
        } else {
            throw new GadNullPointerException("eventCallbackId is null in messageUpdateEventCallbackDefined.");
        }
        if(StringUtils.isNotEmpty(callbackUrl)) {
            postClient.addParameter("callbackUrl", callbackUrl);
        } else {
            throw new GadNullPointerException("callbackUrl is empty in messageUpdateEventCallbackDefined.");
        }
        return postClient.post();
    }
```