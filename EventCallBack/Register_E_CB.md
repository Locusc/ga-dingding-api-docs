# 注册消息回调

## 接口说明
```java
    /**
     * 注册消息回调
     * @param eventTag 消息事件标识
     * @param callbackUrl 消息回调http地址
     * @return java.lang.String
     **/
    String messageRegisterEventCallback(String eventTag, String callbackUrl);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2308)
## 实现方法
```java
    /**
     * 注册消息回调
     * @param eventTag eventTag
     * @param callbackUrl callbackUrl
     * @return java.lang.String
     **/
    @Override
    public String messageRegisterEventCallback(String eventTag, String callbackUrl) {
        PostClient postClient = this.newGadPostClient(GadBECBApiConstants.MESSAGE_REGISTER_EVENT_CALLBACK);
        if(StringUtils.isNotEmpty(eventTag)) {
            postClient.addParameter("eventTag", eventTag);
        } else {
            throw new GadNullPointerException("eventTag is empty in messageRegisterEventCallback");
        }
        if(StringUtils.isNotEmpty(callbackUrl)) {
            postClient.addParameter("callbackUrl", callbackUrl);
        } else {
            throw new GadNullPointerException("callbackUrl is empty in messageRegisterEventCallback");
        }
        return postClient.post();
    }
```