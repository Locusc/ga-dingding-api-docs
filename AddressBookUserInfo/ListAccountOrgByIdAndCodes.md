# 批量根据accountId、tenantId、organizationCode查询这个账号是否在这个租户的这些组织内

## 接口说明
```java
    /**
     * 批量根据accountId、tenantId、organizationCode查询这个账号是否在这个租户的这些组织内
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeListAccountOrgByIdAndCodes(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2353)
## 实现方法
```java
    /**
     * 批量根据accountId、tenantId、organizationCode查询这个账号是否在这个租户的这些组织内
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeListAccountOrgByIdAndCodes(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_LIST_ACCOUNT_ORG_BY_ID_AND_CODES)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("accountId", String.valueOf(jsonObject.getLong("accountId")));
        if (StringUtils.isNotEmpty(jsonObject.getString("organizationCodes"))) {
            postClient.addParameter("organizationCodes", jsonObject.getString("organizationCodes"));
        } else if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("organizationCodes"))) {
            if(jsonObject.getJSONArray("organizationCodes").size() <= 100) {
                jsonObject.getJSONArray("organizationCodes").forEach(code -> {
                    postClient.addParameter("organizationCodes", (String) code);
                });
            } else {
                throw new GadIndexOutOfBoundsException("The length of the organizationCodes is over 100 in employeeListAccountOrgByIdAndCodes");
            }
        }
        return postClient.post();
    }
```