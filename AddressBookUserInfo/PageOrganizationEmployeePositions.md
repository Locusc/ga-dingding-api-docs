# 查询组织下人员详情

## 接口说明
```java
    /**
     * 查询组织下人员详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeePageOrganizationEmployeePositions(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2657)
## 实现方法
```java
    /**
     * 查询组织下人员详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeePageOrganizationEmployeePositions(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_PAGE_ORGANIZATION_EMP_POSITION)
                .addParameter("returnTotalSize", String.valueOf(jsonObject.getBoolean("returnTotalSize")))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("employeeStatus", jsonObject.getString("employeeStatus"))
                .addParameter("organizationCode", jsonObject.getString("organizationCode"))
                .addParameter("pageNo", String.valueOf(jsonObject.getInteger("pageNo")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```