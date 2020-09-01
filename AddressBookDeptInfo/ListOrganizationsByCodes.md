# 根据组织Code列表查询详情

## 接口说明
```java
    /**
     * 根据组织 Code 列表查询详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String deptListOrganizationByCodes(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2297)
## 实现方法
```java
    /**
     * 根据组织 Code 列表查询详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String deptListOrganizationByCodes(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABDIApiConstants.ABDI_LIST_ORGANIZATION_BY_CODES)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        try {
            if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("organizationCodes"))){
                jsonObject.getJSONArray("organizationCodes").forEach(code -> {
                    postClient.addParameter("organizationCodes", String.valueOf(code));
                });
            }
        } catch (Exception e) {
            if(StringUtils.isNotEmpty(jsonObject.getString("organizationCodes"))) {
                postClient.addParameter("organizationCodes", jsonObject.getString("organizationCodes"));
            }
        }
        return postClient.post();
    }
```