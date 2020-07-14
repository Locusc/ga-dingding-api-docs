# 根据行政区划查询行政区划线

## 接口说明
```java
    /**
     * 根据行政区划查询行政区划线
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptGetDivisionLine(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2350)
## 实现方法
```java
    /**
     * 根据行政区划查询行政区划线
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptGetDivisionLine(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_GET_DIVISION_LINE)
                .addParameter("divisionCode", jsonObject.getString("divisionCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```