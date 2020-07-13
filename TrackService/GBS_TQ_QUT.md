# 查询用户轨迹

## 接口说明
```java
    /**
     * 查询用户轨迹
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    String GbsTraceQueryUserTrace(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2501)
## 实现方法
```java
    /**
     * 查询用户轨迹
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    @Override
    public String GbsTraceQueryUserTrace(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadTraceConstants.GBS_TRACE_QUERY_USER_TRACE)
                .addParameter("appName", jsonObject.getString("appName"))
                .addParameter("bizScene", jsonObject.getString("bizScene"))
                .addParameter("accessToken", jsonObject.getString("accessToken"))
                .addParameter("deviceId", jsonObject.getString("deviceId"))
                .addParameter("clientType", jsonObject.getString("clientType"))
                .addParameter("osType", jsonObject.getString("osType"))
                .addParameter("traceId", jsonObject.getString("traceId"))
                .addParameter("startTime", String.valueOf(jsonObject.getLong("startTime")))
                .addParameter("endTime", String.valueOf(jsonObject.getLong("endTime")))
                .addParameter("userId", String.valueOf(jsonObject.getLong("userId")));
        return postClient.post();
    }
```
