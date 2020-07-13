# 查询工作台红点

## 接口说明
```java
    /**
     * 查询工作台红点
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    String messageQueryPortalNotification(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2537)
## 实现方法
```java
    /**
     * 查询工作台红点
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    @Override
    public String messageQueryPortalNotification(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadWNMApiConstants.NOTIFICATION_MESSAGE_QUERY_PORTAL_NOTIFICATION)
                .addParameter("accountId", String.valueOf(jsonObject.getLong("accountId")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```
