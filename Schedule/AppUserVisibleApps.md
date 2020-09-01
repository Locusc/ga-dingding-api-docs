# 获取用户可用的app

## 接口说明
```java
    /**
     * 获取用户可用的app
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String calendarAppUserVisibleApps(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2690)
## 实现方法
```java
    /**
     * 获取用户可用的app
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String calendarAppUserVisibleApps(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadScheduleApiConstants.CALENDAR_USER_VISIBLE_APPS)
                .addParameter("accountId", String.valueOf(jsonObject.getLong("accountId")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("currentPage", String.valueOf(jsonObject.getInteger("currentPage")));
        return postClient.post();
    }
```