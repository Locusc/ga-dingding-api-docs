# 开启轨迹采集

## 接口说明
```java
    /**
     * 开启轨迹采集
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    String GbsTraceStartTraceCollect(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2663)
## 实现方法
```java
    /**
     * 开启轨迹采集
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    @Override
    public String GbsTraceStartTraceCollect(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadTraceConstants.GBS_TRACE_START_TRACE_COLLECT)
                .addParameter("appName", jsonObject.getString("appName"))
                .addParameter("bizScene", jsonObject.getString("bizScene"))
                .addParameter("accessToken", jsonObject.getString("accessToken"))
                .addParameter("deviceId", jsonObject.getString("deviceId"))
                .addParameter("clientType", jsonObject.getString("clientType"))
                .addParameter("osType", jsonObject.getString("osType"))
                .addParameter("traceId", jsonObject.getString("traceId"))
                .addParameter("userId", String.valueOf(jsonObject.getLong("userId")))
                .addParameter("frequency", jsonObject.getJSONObject("frequency").toJSONString())
                .addParameter("reportPeriod", String.valueOf(jsonObject.getInteger("reportPeriod")))
                .addParameter("collectPeriod", String.valueOf(jsonObject.getInteger("collectPeriod")))
                .addParameter("pushPeriod", String.valueOf(jsonObject.getInteger("pushPeriod")));
        return postClient.post();
    }
```