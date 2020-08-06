# 获取通讯录权限范围

## 接口说明
```java
    /**
     * 获取通讯录权限范围
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeAuthScopes(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2638)
## 实现方法
```java
    /**
     * 获取通讯录权限范围
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeAuthScopes(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_AUTH_SCOPES)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```