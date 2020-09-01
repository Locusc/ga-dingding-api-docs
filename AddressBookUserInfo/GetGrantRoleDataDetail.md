# 查询角色授权详情信息

## 接口说明
```java
    /**
     * 查询角色授权详情信息
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeGetGrantRoleDataDetail(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2658)
## 实现方法
```java
    /**
     * 查询角色授权详情信息
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeGetGrantRoleDataDetail(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_ACL_GET_GRANT_ROLE_DATA_DETAIL)
                .addParameter("roleCode", jsonObject.getString("roleCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("employeeCode", jsonObject.getString("employeeCode"));
        return postClient.post();
    }
```