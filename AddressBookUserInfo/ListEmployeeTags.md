# 根据员工Code获取员工标签Code列表

## 接口说明
```java
    /**
     * 根据员工 Code获取员工标签code列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeListEmpTag(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2307)
## 实现方法
```java
    /**
     * 根据员工 Code获取员工标签code列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeListEmpTag(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_LIST_EMPLOYEE_TAGS)
                .addParameter("employeeCode", jsonObject.getString("employeeCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```