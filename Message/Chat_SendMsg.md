# 发送消息

## 接口说明
```java
    /**
     * 发送消息
     * @param jsonObject  JSONObject入参
     * @return java.lang.String
     **/
    String chatSendMsg(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2602)
## 实现方法
```java
    /**
     * 发送消息
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String chatSendMsg(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadChatApiConstants.CHAT_SEND_MSG)
                .addParameter("msg", jsonObject.getString("msg"))
                .addParameter("senderId", jsonObject.getString("senderId"))
                .addParameter("receiverId", jsonObject.getString("receiverId"))
                .addParameter("chatId", jsonObject.getString("chatId"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("chatType", String.valueOf(jsonObject.getInteger("chatType")));
        return postClient.post();
    }
```