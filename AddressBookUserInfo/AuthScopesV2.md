# 获取通讯录权限范围v2

## 接口说明
```java
    /**
     * 获取通讯录权限范围 v2
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeAuthScopesV2(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2641)
## 实现方法
```java
    /**
     * 获取通讯录权限范围 v2
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeAuthScopesV2(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_AUTH_SCOPES_V2)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```