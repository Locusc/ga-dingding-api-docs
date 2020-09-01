# 添加标签

## 接口说明
```java
    /**
     * 添加标签
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeAddTag(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2645)
## 实现方法
```java
    /**
     * 添加标签
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeAddTag(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_TAG_ADD_TAG)
                .addParameter("tagName", jsonObject.getString("tagName"))
                .addParameter("operator", jsonObject.getString("operator"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("tagDescription", jsonObject.getString("tagDescription"));
        try {
            if (!CollectionUtils.isEmpty(jsonObject.getJSONArray("tagGroupCodes"))) {
                jsonObject.getJSONArray("tagGroupCodes").forEach(item -> {
                    postClient.addParameter("tagGroupCodes", String.valueOf(item));
                });
            }
        } catch (Exception e) {
            if(StringUtils.isNotEmpty(jsonObject.getString("tagGroupCodes"))) {
                postClient.addParameter("tagGroupCodes", jsonObject.getString("tagGroupCodes"));
            }
        }
        return postClient.post();
    }
```