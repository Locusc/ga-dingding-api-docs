# 创建群聊会话

## 接口说明
```java
    /**
     * 创建群聊会话 JSONObject入参
     * @param jsonObject
     * @return java.lang.String
     **/
    String imChatIsvCreatGroupChat(JSONObject jsonObject);

    /**
     * 创建群聊会话 ImChatIsvCreatGroupChatObject入参
     * @param imChatIsvCreatGroupChatObject
     * @return java.lang.String
     **/
    String imChatIsvCreatGroupChat(ImChatIsvCreatGroupChatObject imChatIsvCreatGroupChatObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2316)
## 实现方法
```java
    /**
     * 创建群聊会话
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String imChatIsvCreatGroupChat(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadChatApiConstants.IM_CHAT_ISV_CREAT_GROUP_CHAT)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("ownerId", jsonObject.getString("ownerId"))
                .addParameter("title", jsonObject.getString("title"));
        if(StringUtils.isNotEmpty(jsonObject.getString("uids"))) {
            postClient.addParameter("uids", jsonObject.getString("uids"));
        } else if (!CollectionUtils.isEmpty(jsonObject.getJSONArray("uids"))) {
            jsonObject.getJSONArray("uids").forEach(uid -> {
                postClient.addParameter("uids", String.valueOf(uid));
            });
        } else {
            throw new GadNullPointerException("uids is empty in imChatIsvCreatGroupChat.");
        }
        return postClient.post();
    }

    /**
     * 创建群聊会话
     * @param imChatIsvCreatGroupChatObject ImChatIsvCreatGroupChatObject入参
     * @return java.lang.String
     **/
    @Override
    public String imChatIsvCreatGroupChat(ImChatIsvCreatGroupChatObject imChatIsvCreatGroupChatObject) {
        PostClient postClient = this.newGadPostClient(GadChatApiConstants.IM_CHAT_ISV_CREAT_GROUP_CHAT)
                .addParameter("tenantId", String.valueOf(imChatIsvCreatGroupChatObject.getTenantId()))
                .addParameter("ownerId", imChatIsvCreatGroupChatObject.getOwnerId())
                .addParameter("title", imChatIsvCreatGroupChatObject.getTitle());
        if(!CollectionUtils.isEmpty(imChatIsvCreatGroupChatObject.getUids())) {
            imChatIsvCreatGroupChatObject.getUids().forEach(uid -> {
                postClient.addParameter("uids", uid);
            });
        } else {
            throw new GadNullPointerException("uids is empty in imChatIsvCreatGroupChat.");
        }
        return postClient.post();
    }
```