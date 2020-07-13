# 应用更新轨迹推送事件数据

## 接口说明
```java
/**
     * 应用更新轨迹推送事件数据
     * @param id 应用注册id
     * @param callBackUrl 回调地址
     * @return java.lang.String
     **/
    String BipRegisterUpdateEvent(String id, String callBackUrl);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2532)
## 实现方法
```java
    /**
     * 应用更新轨迹推送事件数据
     * @param id 应用注册id
     * @param callBackUrl 回调地址
     * @return java.lang.String
     **/
    @Override
    public String BipRegisterUpdateEvent(String id, String callBackUrl) {
        PostClient postClient = this.newGadPostClient(GadTraceConstants.BIP_REGISTER_UPDATE_EVENT)
                .addParameter("id", id)
                .addParameter("callBackUrl", callBackUrl);
        return postClient.post();
    }
```