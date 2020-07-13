# 删除事件回调的定义信息

## 接口说明
```java
    /**
     * 删除事件回调的定义信息
     * @param eventCallbackId 订阅回调的id
     * @return java.lang.String
     **/
    String messageDeleteEventCallbackDefine(Long eventCallbackId);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2311)
## 实现方法
```java
    /**
     * 删除事件回调的定义信息
     * @param eventCallbackId eventCallbackId
     * @return java.lang.String
     **/
    @Override
    public String messageDeleteEventCallbackDefine(Long eventCallbackId) {
        PostClient postClient = this.newGadPostClient(GadBECBApiConstants.MESSAGE_DELETE_EVENT_CALLBACK_DEFINE);
        if(eventCallbackId != null) {
            postClient.addParameter("eventCallbackId", String.valueOf(eventCallbackId));
        } else {
            throw new GadNullPointerException("eventCallbackId is null in messageDeleteEventCallbackDefine.");
        }
        return postClient.post();
    }
```