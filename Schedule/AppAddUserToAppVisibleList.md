# 设置APP的用户可见性

## 接口说明
```java
    /**
     * 设置APP的用户可见性
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String calendarAppAddUserToAppVisibleList(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2691)
## 实现方法
```java
    /**
     * 设置APP的用户可见性
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String calendarAppAddUserToAppVisibleList(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadScheduleApiConstants.CALENDAR_ADD_USER_TO_APP_VISIBLE_LIST)
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

