# 根据员工Code获取员工的任职

## 接口说明
```java
    /**
     * 根据员工code获取员工的任职
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeListEmpPositionByEmpCode(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2295)
## 实现方法
```java
    /**
     * 根据员工code获取员工的任职
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeListEmpPositionByEmpCode(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_LIST_EMPLOYEES_POSITION_BY_EMPLOYEE_CODE)
                .addParameter("employeePositionStatus", jsonObject.getString("employeePositionStatus"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("employeePositionType", jsonObject.getString("employeePositionType"))
                .addParameter("employeeCode", jsonObject.getString("employeeCode"));
        return postClient.post();
    }
```