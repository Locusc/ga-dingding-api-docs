# 删除员工的任职

## 接口说明
```java
    /**
     * 删除员工的任职
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeDeleteGovEmpPosition(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2306)
## 实现方法
```java
    /**
     * 删除员工的任职
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeDeleteGovEmpPosition(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_DELETE_GOV_EMPLOYEE_POSITION)
                .addParameter("employeeCode", jsonObject.getString("employeeCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("operator", jsonObject.getString("operator"))
                .addParameter("organizationCode", jsonObject.getString("organizationCode"));
        return postClient.post();
    }
```