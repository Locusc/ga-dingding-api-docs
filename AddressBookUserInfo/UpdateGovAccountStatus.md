# 冻结和解冻账号

## 接口说明
```java
    /**
     * 冻结和解冻账号
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeUpdateGovAccountStatus(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2374)
## 实现方法
```java
    /**
     * 冻结和解冻账号
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeUpdateGovAccountStatus(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_UPDATE_GOV_ACCOUNT_STATUS)
                .addParameter("operator", jsonObject.getString("operator"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("namespace", jsonObject.getString("namespace"))
                .addParameter("status", jsonObject.getString("status"))
                .addParameter("account", jsonObject.getString("account"));
        return postClient.post();
    }
```