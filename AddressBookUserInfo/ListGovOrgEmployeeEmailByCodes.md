# 根据组织code和批量员工Code获取员工的邮箱信息

## 接口说明
```java
    /**
     * 根据组织code和批量员工 Code 获取员工的邮箱信息
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeListGovOrgEmpEmailByCodes(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2352)
## 实现方法
```java
    /**
     * 根据组织code和批量员工 Code 获取员工的邮箱信息
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeListGovOrgEmpEmailByCodes(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_LIST_GOV_ORG_EMPLOYEE_EMAIL_BY_CODES)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("organizationCode", String.valueOf(jsonObject.getLong("organizationCode")));
        if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("employeeCodes"))) {
            if(jsonObject.getJSONArray("employeeCodes").size() <= 100) {
                jsonObject.getJSONArray("employeeCodes").forEach(code -> {
                    postClient.addParameter("employeeCodes", (String) code);
                });
            } else {
                throw new GadIndexOutOfBoundsException("The length of the employeeCodes is over 100 in employeeListGovOrgEmpEmailByCodes");
            }
        } else if(StringUtils.isNotEmpty(jsonObject.getString("employeeCodes"))) {
            postClient.addParameter("employeeCodes", jsonObject.getString("employeeCodes"));
        }
        return postClient.post();
    }
```