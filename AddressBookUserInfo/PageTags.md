# 获取标签列表

## 接口说明
```java
    /**
     * 获取标签列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeePageTags(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2652)
## 实现方法
```java
    /**
     * 获取标签列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeePageTags(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_TAG_PAGE_TAGS)
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("pageNo", String.valueOf(jsonObject.getInteger("pageNo")))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("keyword", jsonObject.getString("keyword"));
        return postClient.post();
    }
```