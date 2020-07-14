# 创建组织

## 接口说明
```java
    /**
     * 创建组织
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptCreateGovOrganization(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2300)
## 实现方法
```java
    /**
     * 创建组织
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptCreateGovOrganization(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_CREATE_GOV_ORGANIZATION)
                .addParameter("creator", jsonObject.getString("creator"))
                .addParameter("organizationName", jsonObject.getString("organizationName"))
                .addParameter("displayOrder", String.valueOf(jsonObject.getLong("displayOrder")))
                .addParameter("parentCode", jsonObject.getString("parentCode"))
                .addParameter("organizationType", jsonObject.getString("organizationType"))
                .addParameter("govDivisionCode", jsonObject.getString("govDivisionCode"))
                .addParameter("govShortName", jsonObject.getString("govShortName"))
                .addParameter("govOtherName", jsonObject.getString("govOtherName"))
                .addParameter("govInstitutionCode", jsonObject.getString("govInstitutionCode"))
                .addParameter("govUnifiedSocialCreditCode", jsonObject.getString("govUnifiedSocialCreditCode"))
                .addParameter("govInstitutionLevelCode",jsonObject.getString("govInstitutionLevelCode"))
                .addParameter("govPostalCode", jsonObject.getString("govPostalCode"))
                .addParameter("govRemarks", jsonObject.getString("govRemarks"))
                .addParameter("govContactEmployeeCode", jsonObject.getString("govContactEmployeeCode"))
                .addParameter("govContactNumber", jsonObject.getString("govContactNumber"))
                .addParameter("govAddress", jsonObject.getString("govAddress"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("organizationCode", jsonObject.getString("organizationCode"));
        if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("govBusinessStripCodes"))) {
            jsonObject.getJSONArray("govBusinessStripCodes").forEach(code -> {
                postClient.addParameter("govBusinessStripCodes", String.valueOf(code));
            });
        } else if(StringUtils.isNotEmpty(jsonObject.getString("govBusinessStripCodes"))) {
            postClient.addParameter("govBusinessStripCodes", jsonObject.getString("govBusinessStripCodes"));
        }
        if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("govResponsibleEmployeeCodes"))) {
            jsonObject.getJSONArray("govResponsibleEmployeeCodes").forEach(code -> {
                postClient.addParameter("govResponsibleEmployeeCodes", String.valueOf(code));
            });
        } else if(StringUtils.isNotEmpty(jsonObject.getString("govResponsibleEmployeeCodes"))) {
            postClient.addParameter("govResponsibleEmployeeCodes", jsonObject.getString("govResponsibleEmployeeCodes"));
        }
        return postClient.post();
    }
```