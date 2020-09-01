# 根据员工Code列表查询详情

## 接口说明
```java
    /**
     * 根据员⼯ Code 列表查询详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeListEmpByCodes(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2298)
## 实现方法
```java
    /**
     * 根据员⼯ Code 列表查询详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeListEmpByCodes(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_LIST_EMPLOYEES_BY_CODES)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        try {
            if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("employeeCodes"))) {
                jsonObject.getJSONArray("employeeCodes").forEach(code -> {
                    postClient.addParameter("employeeCodes", String.valueOf(code));
                });
            }
        } catch (Exception e) {
            if (StringUtils.isNotEmpty(jsonObject.getString("employeeCodes"))) {
                postClient.addParameter("employeeCodes", jsonObject.getString("employeeCodes"));
            }
        }
        return postClient.post();
    }
```