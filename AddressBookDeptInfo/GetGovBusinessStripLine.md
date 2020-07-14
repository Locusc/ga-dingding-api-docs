# 根据条线查询条线线

## 接口说明
```java
    /**
     * 根据条线查询条线线
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptGetGovBusinessStripLine(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2347)
## 实现方法
```java
    /**
     * 根据条线查询条线线
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptGetGovBusinessStripLine(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_GET_GOV_BUSINESS_STRIP_LINE)
                .addParameter("businessStripCode", jsonObject.getString("businessStripCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```