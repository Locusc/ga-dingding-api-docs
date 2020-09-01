# 根据组织code查询组织下的员工人数

## 接口说明
```java
    /**
     * 根据组织code查询组织下的员工人数
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptGetOrganizationEmployeeCount(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2659)
## 实现方法
```java
    /**
     * 根据组织code查询组织下的员工人数
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    public String deptGetOrganizationEmployeeCount(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_GET_ORGANIZATION_EMPLOYEE_COUNT)
                .addParameter("organizationCode", jsonObject.getString("organizationCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("employeeStatus", jsonObject.getString("employeeStatus"));
        return postClient.post();
    }
```