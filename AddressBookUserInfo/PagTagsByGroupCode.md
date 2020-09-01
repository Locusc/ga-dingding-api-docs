# 根据标签组code获取标签列表

## 接口说明
```java
    /**
     * 根据标签组code获取标签列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeePagTagsByGroupCode(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2649)
## 实现方法
```java
    /**
     * 根据标签组code获取标签列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeePagTagsByGroupCode(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_TAG_PAGE_TAGS_BY_GROUP_CODE)
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("tagGroupCode", jsonObject.getString("tagGroupCode"))
                .addParameter("pageNo", String.valueOf(jsonObject.getInteger("pageNo")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("status", jsonObject.getString("status"));
        return postClient.post();
    }
```