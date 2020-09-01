# 删除标签

## 接口说明
```java
    /**
     * 删除标签
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeDeleteTag(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2651)
## 实现方法
```java
    /**
     * 删除标签
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeDeleteTag(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_TAG_DELETE_TAGS)
                .addParameter("tagCode", jsonObject.getString("tagCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("operator", jsonObject.getString("operator"));
        return postClient.post();
    }
```