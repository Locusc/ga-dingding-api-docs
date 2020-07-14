# 人员返聘

## 接口说明
```java
    /**
     * 人员返聘
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeRehiredGovEmp(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2540)
## 实现方法
```java
    /**
     * 人员返聘
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeRehiredGovEmp(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_REHIRED_GOV_EMPLOYEE)
                .addParameter("govEmpPosPhoneNo", jsonObject.getString("govEmpPosPhoneNo"))
                .addParameter("orderInOrganization", String.valueOf(jsonObject.getLong("orderInOrganization")))
                .addParameter("operator", jsonObject.getString("operator"))
                .addParameter("employeeCode", jsonObject.getString("employeeCode"))
                .addParameter("govEmpPosEmail", jsonObject.getString("govEmpPosEmail"))
                .addParameter("organizationCode", jsonObject.getString("organizationCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("govEmpPosEmployeeRoleCode", jsonObject.getString("govEmpPosEmployeeRoleCode"))
                .addParameter("govEmpPosFaxNo", jsonObject.getString("govEmpPosFaxNo"))
                .addParameter("govEmpPosJob", jsonObject.getString("govEmpPosJob"))
                .addParameter("govEmpPosAddress", jsonObject.getString("govEmpPosAddress"));
        return postClient.post();
    }
```