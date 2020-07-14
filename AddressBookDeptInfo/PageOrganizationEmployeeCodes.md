# 分页查询组织下的员工Code

## 接口说明
```java
    /**
     * 分页查询组织下的员⼯ Code
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptPageOrganizationEmployeeCodes(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2292)
## 实现方法
```java
    /**
     * 分页查询组织下的员⼯ Code
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptPageOrganizationEmployeeCodes(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_PAGE_ORGANIZATION_EMPLOYEE_CODES)
                .addParameter("returnTotalSize", String.valueOf(jsonObject.getBoolean("returnTotalSize")))
                .addParameter("employeePositionStatus", jsonObject.getString("employeePositionStatus"))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("pageNo", String.valueOf(jsonObject.getInteger("pageNo")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("organizationCode", jsonObject.getString("organizationCode"));
        return postClient.post();
    }
```