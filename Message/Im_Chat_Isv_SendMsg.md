# 发送IM消息

## 接口说明
```java
    /**
     * 发送IM消息 JSONObject入参
     * @param jsonObject
     * @return java.lang.String
     **/
    String imChatIsvSendMsg(JSONObject jsonObject);

    /**
     * 发送IM消息 ImChatIsvSendMsgObject入参
     * @param imChatIsvSendMsgObject
     * @return java.lang.String
     **/
    String imChatIsvSendMsg(ImChatIsvSendMsgObject imChatIsvSendMsgObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2317)
## 实现方法
```java
    /**
     * 发送IM消息
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String imChatIsvSendMsg(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadChatApiConstants.IM_CHAT_ISV_SEND_MSG)
                .addParameter("msg", jsonObject.getString("msg"))
                .addParameter("senderId", jsonObject.getString("senderId"))
                .addParameter("receiverId", jsonObject.getString("receiverId"))
                .addParameter("cid", jsonObject.getString("cid"))
                .addParameter("chatType", String.valueOf(jsonObject.getInteger("chatType")));
        return postClient.post();
    }

    /**
     * 发送IM消息
     * @param imChatIsvSendMsgObject ImChatIsvSendMsgObject入参
     * @return java.lang.String
     **/
    @Override
    public String imChatIsvSendMsg(ImChatIsvSendMsgObject imChatIsvSendMsgObject) {
        PostClient postClient = this.newGadPostClient(GadChatApiConstants.IM_CHAT_ISV_SEND_MSG)
                .addParameter("msg", imChatIsvSendMsgObject.getMsg())
                .addParameter("senderId", imChatIsvSendMsgObject.getSenderId())
                .addParameter("receiverId", imChatIsvSendMsgObject.getReceiverId())
                .addParameter("cid", imChatIsvSendMsgObject.getCid())
                .addParameter("chatType", String.valueOf(imChatIsvSendMsgObject.getChatType()));
        return postClient.post();
    }
```