# 人员排序

## 接口说明
```java
    /**
     * 人员排序
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeReorderEmpPositionsByCodes(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2664)
## 实现方法
```java
    /**
     * 人员排序
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeReorderEmpPositionsByCodes(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_REORDER_EMP_POSITION_BY_CODES)
                .addParameter("organizationCode", jsonObject.getString("fromOrganizationCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("operator", jsonObject.getString("operator"));
        try {
            if (!CollectionUtils.isEmpty(jsonObject.getJSONArray("employeeCodes"))) {
                jsonObject.getJSONArray("employeeCodes").forEach(item -> {
                    postClient.addParameter("employeeCodes", String.valueOf(item));
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