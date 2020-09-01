# isv或外部服务生成轨迹id

## 接口说明
```java
    /**
     * isv或外部服务生成轨迹id
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    String GbsTraceGenerateTraceIdByIsv(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2498)
## 实现方法
```java
    /**
     * isv或外部服务生成轨迹id
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    @Override
    public String GbsTraceGenerateTraceIdByIsv(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadTraceConstants.GBS_TRACE_GENERATE_TRACE_ID_BY_ISV)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("userId", String.valueOf(jsonObject.getLong("userId")))
                .addParameter("employeeCode", jsonObject.getString("employeeCode"));
        return postClient.post();
    }
```