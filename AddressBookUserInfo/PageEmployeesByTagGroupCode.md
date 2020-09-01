# 根据标签组code获取人员信息列表

## 接口说明
```java
    /**
     * 根据标签组code获取人员信息列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeePageEmployeesByTagGroupCode(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2643)
## 实现方法
```java
    /**
     * 根据标签组code获取人员信息列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeePageEmployeesByTagGroupCode(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_PAGE_EMP_BY_TAG_GROUP_CODE)
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("tagGroupCode", jsonObject.getString("tagGroupCode"))
                .addParameter("pageNo", String.valueOf(jsonObject.getInteger("pageNo")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```