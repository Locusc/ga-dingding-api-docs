# 移除失败回调

## 接口说明
```java
    /**
     * 移除失败回调
     * @param eventCallbackFailedId 失败的id
     * @return java.lang.String
     **/
    String messageRemoveCallbackFailed(Long eventCallbackFailedId);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2314)
## 实现方法
```java
    /**
     * 移除失败回调
     * @param eventCallbackFailedId eventCallbackFailedId
     * @return java.lang.String
     **/
    @Override
    public String messageRemoveCallbackFailed(Long eventCallbackFailedId) {
        PostClient postClient = this.newGadPostClient(GadBECBApiConstants.MESSAGE_REMOVE_CALLBACK_FAILED);
        if(eventCallbackFailedId != null) {
            postClient.addParameter("eventCallbackFailedId", String.valueOf(eventCallbackFailedId));
        } else {
            throw new GadNullPointerException("eventCallbackFailedId is null in messageRemoveCallbackFailed.");
        }
        return postClient.post();
    }
```