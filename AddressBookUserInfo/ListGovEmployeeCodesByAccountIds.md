# 批量通过账号Id列表获取人员Code

## 接口说明
```java
    /**
     * 批量 通过账号Id 列表获取人员Code
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeListGovEmpCodesByAccountIds(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2343)
## 实现方法
```java
    /**
     * 批量 通过账号Id 列表获取人员Code
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeListGovEmpCodesByAccountIds(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_LIST_GOV_EMPLOYEE_CODES_BY_ACCOUNT_IDS)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        try {
            if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("accountIds"))) {
                jsonObject.getJSONArray("accountIds").forEach(id -> {
                    postClient.addParameter("accountIds", (String) id);
                });
            }
        } catch (Exception e) {
            if(jsonObject.getLong("accountIds") != null) {
                postClient.addParameter("accountIds", String.valueOf(jsonObject.getLong("accountIds")));
            }
        }
        return postClient.post();
    }
```