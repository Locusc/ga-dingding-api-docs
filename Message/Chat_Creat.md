# 创建群会话

## 接口说明
```java
    /**
     * 创建群会话
     * @param jsonObject  JSONObject入参
     * @return java.lang.String
     **/
    String chatCreate(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2600)
## 实现方法
```java
    /**
     * 创建群会话
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String chatCreate(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadChatApiConstants.CHAT_CREATE)
                .addParameter("accountId", String.valueOf(jsonObject.getLong("accountId")))
                .addParameter("disableRead", String.valueOf(jsonObject.getInteger("disableRead")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("name", jsonObject.getString("name"))
                .addParameter("managementType", String.valueOf(jsonObject.getInteger("managementType")));
        if(StringUtils.isNotEmpty(jsonObject.getString("useridlist"))) {
            postClient.addParameter("useridlist", jsonObject.getString("useridlist"));
        } else if (!CollectionUtils.isEmpty(jsonObject.getJSONArray("useridlist"))) {
            jsonObject.getJSONArray("useridlist").forEach(uid -> {
                postClient.addParameter("useridlist", String.valueOf(uid));
            });
        } else {
            throw new GadNullPointerException("useridlist is empty in chatCreate.");
        }
        return postClient.post();
    }
```