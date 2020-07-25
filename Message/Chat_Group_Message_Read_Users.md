# 获取消息已读人数

## 接口说明
```java
    /**
     * 获取消息已读人数
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String chatGroupMessageReadUsers(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2604)
## 实现方法
```java
    /**
     * 获取消息已读人数
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String chatGroupMessageReadUsers(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadChatApiConstants.CHAT_GROUP_MESSAGE_READ_USERS)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("accountId", String.valueOf(jsonObject.getLong("accountId")))
                .addParameter("messageId", jsonObject.getString("messageId"))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("cursor", String.valueOf(jsonObject.getLong("cursor")));
        return postClient.post();
    }
```