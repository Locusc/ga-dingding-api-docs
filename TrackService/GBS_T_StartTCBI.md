# 外部服务开启轨迹采集

## 接口说明
```java
    /**
     * 外部服务开启轨迹采集
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    String GbsTraceStartTraceCollectByIsv(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2499)
## 实现方法
```java
    /**
     * 外部服务开启轨迹采集
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    @Override
    public String GbsTraceStartTraceCollectByIsv(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadTraceConstants.GBS_TRACE_START_TRACE_COLLECT_BY_ISV)
                .addParameter("traceId", jsonObject.getString("traceId"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("userId", String.valueOf(jsonObject.getLong("userId")))
                .addParameter("frequency", jsonObject.getJSONObject("frequency").toJSONString())
                .addParameter("employeeCode", jsonObject.getString("employeeCode"))
                .addParameter("reportPeriod", String.valueOf(jsonObject.getInteger("reportPeriod")))
                .addParameter("collectPeriod", String.valueOf(jsonObject.getInteger("collectPeriod")))
                .addParameter("pushPeriod", String.valueOf(jsonObject.getInteger("pushPeriod")));
        return postClient.post();
    }
```
