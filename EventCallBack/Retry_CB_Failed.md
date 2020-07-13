# 重试失败回调

## 接口说明
```java
    /**
     * 重试失败回调
     * @param eventCallbackFailedId 回调失败的id
     * @return java.lang.String
     **/
    String messageRetryCallbackFailed(Long eventCallbackFailedId);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2313)
## 实现方法
```java
    /**
     * 重试失败回调
     * @param eventCallbackFailedId eventCallbackFailedId
     * @return java.lang.String
     **/
    @Override
    public String messageRetryCallbackFailed(Long eventCallbackFailedId) {
        PostClient postClient = this.newGadPostClient(GadBECBApiConstants.MESSAGE_RETRY_CALLBACK_FAILED);
        if(eventCallbackFailedId != null) {
            postClient.addParameter("eventCallbackFailedId", String.valueOf(eventCallbackFailedId));
        } else {
            throw new GadNullPointerException("eventCallbackFailedId is null in messageRetryCallbackFailed.");
        }
        return postClient.post();
    }
```