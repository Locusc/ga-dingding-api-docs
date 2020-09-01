# 更新群会话

## 接口说明
```java
    /**
     * 更新群会话
     * @param jsonObject  JSONObject入参
     * @return java.lang.String
     **/
    String chatGroupUpdate(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2661)
## 实现方法
```java
    /**
     * 更新群会话
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    public String chatGroupUpdate(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadChatApiConstants.CHAT_GROUP_UPDATE)
                .addParameter("chatId", jsonObject.getString("chatId"))
                .addParameter("newOwnerAccountId", String.valueOf(jsonObject.getInteger("newOwnerAccountId")))
                .addParameter("icon", jsonObject.getString("icon"))
                .addParameter("managementType", String.valueOf(jsonObject.getInteger("managementType")))
                .addParameter("accountId", String.valueOf(jsonObject.getLong("accountId")))
                .addParameter("disableRead", String.valueOf(jsonObject.getInteger("disableRead")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("name", jsonObject.getString("name"))
                .addParameter("silenceAll", String.valueOf(jsonObject.getInteger("silenceAll")));
        try {
            if (!CollectionUtils.isEmpty(jsonObject.getJSONArray("addUserIdList"))) {
                jsonObject.getJSONArray("addUserIdList").forEach(uid -> {
                    postClient.addParameter("addUserIdList", String.valueOf(uid));
                });
            }
        } catch (Exception e) {
            if(StringUtils.isNotEmpty(jsonObject.getString("addUserIdList"))) {
                postClient.addParameter("addUserIdList", jsonObject.getString("addUserIdList"));
            }
        }
        try {
            if (!CollectionUtils.isEmpty(jsonObject.getJSONArray("delUserIdList"))) {
                jsonObject.getJSONArray("delUserIdList").forEach(uid -> {
                    postClient.addParameter("delUserIdList", String.valueOf(uid));
                });
            }
        } catch (Exception e) {
            if(StringUtils.isNotEmpty(jsonObject.getString("delUserIdList"))) {
                postClient.addParameter("delUserIdList", jsonObject.getString("delUserIdList"));
            }
        }
        return postClient.post();
    }
```