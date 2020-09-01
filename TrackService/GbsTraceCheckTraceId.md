# 校验轨迹id

## 接口说明
```java
    /**
     * 校验轨迹id
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    String GbsTraceCheckTraceId(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2662)
## 实现方法
```java
    /**
     * 校验轨迹id
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    @Override
    public String GbsTraceCheckTraceId(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadTraceConstants.GBS_TRACE_CHECK_TRACE_ID)
                .addParameter("appName", jsonObject.getString("appName"))
                .addParameter("bizScene", jsonObject.getString("bizScene"))
                .addParameter("accessToken", jsonObject.getString("accessToken"))
                .addParameter("deviceId", jsonObject.getString("deviceId"))
                .addParameter("clientType", jsonObject.getString("clientType"))
                .addParameter("osType", jsonObject.getString("osType"))
                .addParameter("traceId", jsonObject.getString("traceId"))
                .addParameter("userId", String.valueOf(jsonObject.getLong("userId")));
        return postClient.post();
    }
```