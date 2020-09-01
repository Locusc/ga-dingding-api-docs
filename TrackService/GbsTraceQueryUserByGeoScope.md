# 根据位置范围查询用户

## 接口说明
```java
    /**
     * 根据位置范围查询用户
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    String GbsTraceQueryUserByGeoScope(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2660)
## 实现方法
```java
    /**
     * 根据位置范围查询用户
     * @param jsonObject jsonObject入参
     * @return java.lang.String
     **/
    @Override
    public String GbsTraceQueryUserByGeoScope(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadTraceConstants.GBS_TRACE_QUERY_USER_BY_GEO_SCOPE)
                .addParameter("searchLimitTime", String.valueOf(jsonObject.getLong("searchLimitTime")))
                .addParameter("geoType", String.valueOf(jsonObject.getInteger("geoType")))
                .addParameter("latitude", String.valueOf(jsonObject.getDouble("latitude")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("radius", String.valueOf(jsonObject.getDouble("radius")))
                .addParameter("longitude", String.valueOf(jsonObject.getDouble("longitude")));
        return postClient.post();
    }
```