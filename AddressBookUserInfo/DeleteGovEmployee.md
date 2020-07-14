# 删除员工

## 接口说明
```java
    /**
     * 删除员工
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeDeleteGovEmp(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2305)
## 实现方法
```java
     /**
      * 删除员工
      * @param jsonObject JSONObject入参
      * @return java.lang.String
      **/
     @Override
     public String employeeDeleteGovEmp(JSONObject jsonObject) {
         PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_DELETE_GOV_EMPLOYEE)
                 .addParameter("employeeCode", jsonObject.getString("employeeCode"))
                 .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                 .addParameter("operator", jsonObject.getString("operator"));
         return postClient.post();
     }
```