# 接收轨迹数据

## 接口说明
```java
    /**
     * 接收轨迹数据
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    String GbsTraceReceiveTraceData(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2497)
## 实现方法
```java
    /**
     * 接收轨迹数据
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    @Override
    public String GbsTraceReceiveTraceData(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadTraceConstants.GBS_TRACE_RECEIVE_TRACE_DATA)
                .addParameter("appName", jsonObject.getString("appName"))
                .addParameter("bizScene", jsonObject.getString("bizScene"))
                .addParameter("accessToken", jsonObject.getString("accessToken"))
                .addParameter("deviceId", jsonObject.getString("deviceId"))
                .addParameter("clientType", jsonObject.getString("clientType"))
                .addParameter("osType", jsonObject.getString("osType"))
                .addParameter("traceId", jsonObject.getString("traceId"))
                .addParameter("positions", jsonObject.getString("positions"));
        return postClient.post();
    }
```