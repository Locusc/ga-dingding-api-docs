# 删除标签组

## 接口说明
```java
    /**
     * 删除标签组
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeDeleteTagGroup(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2650)
## 实现方法
```java
    /**
     * 删除标签组
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeDeleteTagGroup(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_TAG_DELETE_TAG_GROUP)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("tagGroupCode", jsonObject.getString("tagGroupCode"))
                .addParameter("operator", jsonObject.getString("operator"));
        return postClient.post();
    }
```