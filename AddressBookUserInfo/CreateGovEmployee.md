# 新增员工

## 接口说明
```java
    /**
     * 新增员工
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeCreateGovEmp(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2303)
## 实现方法
```java
    /**
     * 新增员工
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeCreateGovEmp(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_CREATE_GOV_EMPLOYEE)
                .addParameter("sendActiveSms", String.valueOf(jsonObject.getBoolean("sendActiveSms")))
                .addParameter("govEmpJobLevelCode", jsonObject.getString("govEmpJobLevelCode"))
                .addParameter("govEmpBudgetedPostCode", jsonObject.getString("govEmpBudgetedPostCode"))
                .addParameter("operator", jsonObject.getString("operator"))
                .addParameter("employeeCode", jsonObject.getString("employeeCode"))
                .addParameter("operator", jsonObject.getString("operator"))
                .addParameter("employeeCode", jsonObject.getString("employeeCode"))
                .addParameter("govEmpCellPhoneShortNo", jsonObject.getString("govEmpCellPhoneShortNo"))
                .addParameter("password", jsonObject.getString("password"))
                .addParameter("govEmpGenderCode", jsonObject.getString("govEmpGenderCode"))
                .addParameter("govEmpRemarks", jsonObject.getString("govEmpRemarks"))
                .addParameter("govEmpBirthDate", jsonObject.getDate("govEmpBirthDate").toString())
                .addParameter("employeeName", jsonObject.getString("employeeName"))
                .addParameter("govEmpCellPhoneNo", jsonObject.getString("govEmpCellPhoneNo"))
                .addParameter("govEmpHomeAddress", jsonObject.getString("govEmpHomeAddress"))
                .addParameter("areaCode", jsonObject.getString("areaCode"))
                .addParameter("govEmpAvatar", jsonObject.getString("govEmpAvatar"))
                .addParameter("govEmpIdentityCardNo", jsonObject.getString("govEmpIdentityCardNo"))
                .addParameter("namespace", jsonObject.getString("namespace"))
                .addParameter("account", jsonObject.getString("account"))
                .addParameter("govEmpPoliticalStatusCode", jsonObject.getString("govEmpPoliticalStatusCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```