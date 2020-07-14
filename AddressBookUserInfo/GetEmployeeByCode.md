# 根据员工Code查询详情

## 接口说明
```java
    /**
     * 根据员工 Code 查询详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeGetEmpByCode(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2294)
## 实现方法
```java
    /**
     * 根据员工 Code 查询详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeGetEmpByCode(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_GET_EMPLOYEE_BY_CODE)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("employeeCode", jsonObject.getString("employeeCode"));
        return postClient.post();
    }
```