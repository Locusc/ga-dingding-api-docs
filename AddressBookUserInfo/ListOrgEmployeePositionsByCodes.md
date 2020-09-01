# 根据组织Code,员工Code列表,批量获取员工在该组织的任职

## 接口说明
```java
    /**
     * 根据组织 CODE、员⼯ Code 列表， 批量获取员工在该组织的任职
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeListOrgEmpPositionByCodes(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2299)
## 实现方法
```java
    /**
     * 根据组织 CODE、员⼯ Code 列表， 批量获取员工在该组织的任职
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeListOrgEmpPositionByCodes(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_LIST_ORG_EMPLOYEE_POSITION_BY_CODES)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("organizationCode", jsonObject.getString("organizationCode"));
        try {
            if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("employeeCodes"))) {
                jsonObject.getJSONArray("employeeCodes").forEach(code -> {
                    postClient.addParameter("employeeCodes", String.valueOf(code));
                });
            }
        } catch (Exception e) {
            if(StringUtils.isNotEmpty(jsonObject.getString("employeeCodes"))) {
                postClient.addParameter("employeeCodes", jsonObject.getString("employeeCodes"));
            }
        }
        return postClient.post();
    }
```