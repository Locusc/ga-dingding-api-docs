# 发送工作台红点

## 接口说明
```java
    /**
     * 发送工作台红点
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    String messageSendPortalNotification(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2539)
## 实现方法
```java
    /**
     * 发送工作台红点
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    @Override
    public String messageSendPortalNotification(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadWNMApiConstants.NOTIFICATION_MESSAGE_SEND_PORTAL_NOTIFICATION)
                .addParameter("accountId", String.valueOf(jsonObject.getLong("accountId")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        if(StringUtils.isNotEmpty(jsonObject.getString("addNum"))) {
            postClient.addParameter("addNum", jsonObject.getString("addNum"));
        } else {
            if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("bizMsgIds"))) {
                jsonObject.getJSONArray("bizMsgIds").forEach(id -> {
                    postClient.addParameter("bizMsgIds", (String) id);
                });
            } else {
                postClient.addParameter("bizMsgIds", jsonObject.getString("bizMsgIds"));
            }
        }
        return postClient.post();
    }
```