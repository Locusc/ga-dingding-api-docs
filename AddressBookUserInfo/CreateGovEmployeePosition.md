# 创建员工的任职

## 接口说明
```java
    /**
     * 创建员工的任职
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeCreateGovEmpPosition(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2318)
## 实现方法
```java
    /**
     * 创建员工的任职
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeCreateGovEmpPosition(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_CREATE_GOV_EMPLOYEE_POSITION)
                .addParameter("creator", jsonObject.getString("creator"))
                .addParameter("posJobRankCode", jsonObject.getString("posJobRankCode"))
                .addParameter("govEmpPosPhoneNo", jsonObject.getString("govEmpPosPhoneNo"))
                .addParameter("govJobAttributesCode", jsonObject.getString("govJobAttributesCode"))
                .addParameter("orderInOrganization", String.valueOf(jsonObject.getLong("orderInOrganization")))
                .addParameter("mainJob", String.valueOf(jsonObject.getBoolean("mainJob")))
                .addParameter("employeeCode", jsonObject.getString("employeeCode"))
                .addParameter("govEmpPosEmail", jsonObject.getString("govEmpPosEmail"))
                .addParameter("organizationCode", jsonObject.getString("organizationCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("govEmpPosEmployeeRoleCode", jsonObject.getString("govEmpPosEmployeeRoleCode"))
                .addParameter("govEmpPosFaxNo", jsonObject.getString("govEmpPosFaxNo"))
                .addParameter("govEmpPosJob", jsonObject.getString("govEmpPosJob"))
                .addParameter("govEmpPosAddress", jsonObject.getString("govEmpPosAddress"))
                .addParameter("order", String.valueOf(jsonObject.getLong("order")));
        return postClient.post();
    }
```