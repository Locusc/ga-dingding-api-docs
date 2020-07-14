# 根据组织code查询详情

## 接口说明
```java
    /**
     * 根据组织code查询详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptGetOrganizationByCode(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2291)
## 实现方法
```java
    /**
     * 根据组织code查询详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptGetOrganizationByCode(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_GET_ORGANIZATION_BY_CODE)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("organizationCode", jsonObject.getString("organizationCode"));
        return postClient.post();
    }
```