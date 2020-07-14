# 根据组织查询组织汇报线

## 接口说明
```java
    /**
     * 根据组织查询组织汇报线
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptGetOrganizationLine(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2296)
## 实现方法
```java
    /**
     * 根据组织查询组织汇报线
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptGetOrganizationLine(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_GET_ORGANIZATION_LINE)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("organizationCode", jsonObject.getString("organizationCode"));
        return postClient.post();
    }
```