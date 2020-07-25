# 根据手机号码获取人员编码

## 接口说明
```java
    /**
     * 移动任职
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeGetMoveEmpPosition(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2601)
## 实现方法
```java
    /**
     * 移动任职
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeGetMoveEmpPosition(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_GET_MOVE_EMP_POSITION)
                .addParameter("toOrganizationCode", jsonObject.getString("toOrganizationCode"))
                .addParameter("fromOrganizationCode", jsonObject.getString("fromOrganizationCode"))
                .addParameter("operator", jsonObject.getString("operator"))
                .addParameter("employeeCode", jsonObject.getString("employeeCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```