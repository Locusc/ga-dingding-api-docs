# 根据标签code获取人员信息列表

## 接口说明
```java
    /**
     * 根据标签code获取人员信息列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeePageEmployeesByTagCode(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2654)
## 实现方法
```java
    /**
     * 根据标签code获取人员信息列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeePageEmployeesByTagCode(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_PAGE_EMP_BY_TAG_CODE)
                .addParameter("tagCode", jsonObject.getString("tagCode"))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("pageNo", String.valueOf(jsonObject.getInteger("pageNo")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```