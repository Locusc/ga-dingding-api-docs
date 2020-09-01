# 获取APP设置可见的用户Id

## 接口说明
```java
    /**
     * 获取APP设置可见的用户Id
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String calendarAppQueryAppVisibleList(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2691)
## 实现方法
```java
    /**
     * 获取APP设置可见的用户Id
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String calendarAppQueryAppVisibleList(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadScheduleApiConstants.CALENDAR_QUERY_APP_VISIBLE_LIST)
                .addParameter("appName", jsonObject.getString("appName"))
                .addParameter("bizScene", jsonObject.getString("bizScene"))
                .addParameter("clientType", jsonObject.getString("clientType"))
                .addParameter("osType", jsonObject.getString("osType"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("currentPage", String.valueOf(jsonObject.getInteger("currentPage")));
        return postClient.post();
    }
```