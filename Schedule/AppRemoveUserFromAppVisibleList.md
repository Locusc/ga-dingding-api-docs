# 从可见用户列表中删除指定用户

## 接口说明
```java
    /**
     * 从可见用户列表中删除指定用户
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String calendarAppRemoveUserFromAppVisibleList(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2692)
## 实现方法
```java
    /**
     * 从可见用户列表中删除指定用户
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String calendarAppRemoveUserFromAppVisibleList(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadScheduleApiConstants.CALENDAR_REMOVE_USER_FROM_APP_VISIBLE_LIST)
                .addParameter("appName", jsonObject.getString("appName"))
                .addParameter("bizScene", jsonObject.getString("bizScene"))
                .addParameter("clientType", jsonObject.getString("clientType"))
                .addParameter("osType", jsonObject.getString("osType"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("accountIds"))) {
            jsonObject.getJSONArray("accountIds").forEach(item -> {
                postClient.addParameter("accountIds", String.valueOf(item));
            });
        }
        return postClient.post();
    }
```