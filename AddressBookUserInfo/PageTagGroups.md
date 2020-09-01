# 获取所有标签组

## 接口说明
```java
    /**
     * 获取所有标签组
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeePageTagGroups(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2644)
## 实现方法
```java
    /**
     * 获取所有标签组
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeePageTagGroups(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_TAG_PAGE_TAG_GROUPS)
                .addParameter("returnTotalSize", String.valueOf(jsonObject.getBoolean("returnTotalSize")))
                .addParameter("pageNo", String.valueOf(jsonObject.getInteger("pageNo")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")));
        return postClient.post();
    }
```