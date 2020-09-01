# 创建日历事件

## 接口说明
```java
    /**
     * 创建日历事件
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String calendarCreateCalendarEvent(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2358)
## 实现方法
```java
    /**
     * 创建日历事件
     * @param jsonObject  JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String calendarCreateCalendarEvent(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadScheduleApiConstants.CALENDAR_CREATE_CALENDAR)
                .addParameter("appName", jsonObject.getString("appName"))
                .addParameter("bizScene", jsonObject.getString("bizScene"))
                .addParameter("clientType", jsonObject.getString("clientType"))
                .addParameter("osType", jsonObject.getString("osType"))
                .addParameter("summary", jsonObject.getString("summary"))
                .addParameter("creator", jsonObject.getJSONObject("creator").toJSONString())
                .addParameter("start", jsonObject.getJSONObject("start").toJSONString())
                .addParameter("description", jsonObject.getString("description"))
                .addParameter("eventType", jsonObject.getString("eventType"))
                .addParameter("calendarId", String.valueOf(jsonObject.getLong("calendarId")))
                .addParameter("attendeeNum", String.valueOf(jsonObject.getLong("attendeeNum")))
                .addParameter("sourceType", jsonObject.getString("sourceType"))
                .addParameter("bizId", jsonObject.getString("bizId"))
                .addParameter("confirmStatus", jsonObject.getString("confirmStatus"))
                .addParameter("acceptedNum", String.valueOf(jsonObject.getLong("acceptedNum")))
                .addParameter("end", jsonObject.getJSONObject("end").toJSONString())
                .addParameter("pageQueryDto", jsonObject.getJSONObject("pageQueryDto").toJSONString())
                .addParameter("sourceName", jsonObject.getString("sourceName"))
                .addParameter("event", jsonObject.getJSONObject("event").toJSONString())
                .addParameter("accountId", String.valueOf(jsonObject.getLong("accountId")))
                .addParameter("image", jsonObject.getString("image"))
                .addParameter("phone", jsonObject.getString("phone"))
                .addParameter("displayName", jsonObject.getString("displayName"))
                .addParameter("tenantId", jsonObject.getString("tenantId"))
                .addParameter("position", jsonObject.getString("position"))
                .addParameter("accountId", String.valueOf(jsonObject.getLong("accountId")))
                .addParameter("image", jsonObject.getString("image"))
                .addParameter("phone", jsonObject.getString("phone"))
                .addParameter("displayName", jsonObject.getString("displayName"))
                .addParameter("tenantId", jsonObject.getString("tenantId"))
                .addParameter("position", jsonObject.getString("position"))
                .addParameter("timeStamp", String.valueOf(jsonObject.getLong("timeStamp")))
                .addParameter("dateTime", jsonObject.getString("dateTime"))
                .addParameter("timeZone", jsonObject.getString("timeZone"))
                .addParameter("organizationId", String.valueOf(jsonObject.getLong("organizationId")))
                .addParameter("accountId", String.valueOf(jsonObject.getLong("accountId")))
                .addParameter("image", jsonObject.getString("image"))
                .addParameter("phone", jsonObject.getString("phone"))
                .addParameter("displayName", jsonObject.getString("displayName"))
                .addParameter("tenantId", jsonObject.getString("tenantId"))
                .addParameter("position", jsonObject.getString("position"))
                .addParameter("attendeeType", jsonObject.getString("attendeeType"))
                .addParameter("organizationId", String.valueOf(jsonObject.getLong("organizationId")))
                .addParameter("accountId", String.valueOf(jsonObject.getLong("accountId")))
                .addParameter("image", jsonObject.getString("image"))
                .addParameter("phone", jsonObject.getString("phone"))
                .addParameter("displayName", jsonObject.getString("displayName"))
                .addParameter("tenantId", jsonObject.getString("tenantId"))
                .addParameter("position", jsonObject.getString("position"))
                .addParameter("attendeeType", jsonObject.getString("attendeeType"))
                .addParameter("timeStamp", String.valueOf(jsonObject.getLong("timeStamp")))
                .addParameter("dateTime", jsonObject.getString("dateTime"))
                .addParameter("timeZone", jsonObject.getString("timeZone"))
                .addParameter("returnTotalSize", String.valueOf(jsonObject.getBoolean("returnTotalSize")))
                .addParameter("pageNo", String.valueOf(jsonObject.getInteger("pageNo")))
                .addParameter("pageNoSize", String.valueOf(jsonObject.getInteger("pageNoSize")));
        try {
            if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("attendees"))) {
                jsonObject.getJSONArray("attendees").forEach(item -> {
                    postClient.addParameter("attendees", String.valueOf(item));
                });
            }
        } catch (Exception e) {
            if(jsonObject.getJSONObject("attendees").toJSONString() != null) {
                postClient.addParameter("attendees", jsonObject.getJSONObject("attendees").toJSONString());
            }
        }
        try {
            if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("attendeesAdd"))) {
                jsonObject.getJSONArray("attendeesAdd").forEach(item -> {
                    postClient.addParameter("attendeesAdd", String.valueOf(item));
                });
            }
        } catch (Exception e) {
            if(jsonObject.getJSONObject("attendeesAdd").toJSONString() != null) {
                postClient.addParameter("attendeesAdd", jsonObject.getJSONObject("attendeesAdd").toJSONString());
            }
        }
        try {
            if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("attendeesDel"))) {
                jsonObject.getJSONArray("attendeesDel").forEach(item -> {
                    postClient.addParameter("attendeesDel", String.valueOf(item));
                });
            }
        } catch (Exception e) {
            if(jsonObject.getJSONObject("attendeesDel").toJSONString() != null) {
                postClient.addParameter("attendeesDel", jsonObject.getJSONObject("attendeesDel").toJSONString());
            }
        }
        return postClient.post();
    }
```