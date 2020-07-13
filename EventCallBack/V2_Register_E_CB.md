# 注册消息回调(支持加密,签名)

## 接口说明
```java
    /**
     * 注册消息回调
     * @param eventTag 消息事件标识
     * @param callbackUrl 消息回调http地址
     * @return java.lang.String
     **/
    String messageV2RegisterEventCallback(String eventTag, String callbackUrl);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2505)
## 实现方法
```java
    /**
     * 注册消息回调（支持加密、签名）
     * @param eventTag eventTag
     * @param callbackUrl callbackUrl
     * @return java.lang.String
     **/
    @Override
    public String messageV2RegisterEventCallback(String eventTag, String callbackUrl) {
        PostClient postClient = this.newGadPostClient(GadBECBApiConstants.MESSAGE_V2_REGISTER_EVENT_CALLBACK);
        if(StringUtils.isEmpty(eventTag)) {
            throw new GadNullPointerException("eventTag is empty in messageRegisterEventCallback");
        } else {
            postClient.addParameter("eventTag", eventTag);
        }
        if(StringUtils.isEmpty(callbackUrl)) {
            throw new GadNullPointerException("callbackUrl is empty in messageRegisterEventCallback");
        } else {
            postClient.addParameter("callbackUrl", callbackUrl);
        }
        return postClient.post();
    }
```