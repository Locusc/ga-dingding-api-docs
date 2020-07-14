# 通过员工Code列表获取员工账号ID

## 接口说明
```java
    /**
     * 通过员工 Code 列表获取员⼯账号 ID
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeListEmpAccountIds(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2293)
## 实现方法
```java
    /**
     * 通过员工 Code 列表获取员⼯账号 ID
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeListEmpAccountIds(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_LIST_EMPLOYEE_ACCOUNT_IDS)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        if (StringUtils.isNotEmpty(jsonObject.getString("employeeCodes"))) {
            postClient.addParameter("employeeCodes", jsonObject.getString("employeeCodes"));
        } else if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("employeeCodes"))) {
            jsonObject.getJSONArray("employeeCodes").forEach(code -> {
                postClient.addParameter("employeeCodes", (String) code);
            });
        }
        return postClient.post();
    }
```