# 根据标签code列表获取标签详情

## 接口说明
```java
    /**
     * 根据标签code列表获取标签详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeGetTagsDetailByCodes(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2647)
## 实现方法
```java
    /**
     * 根据标签code列表获取标签详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeGetTagsDetailByCodes(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_TAG_GET_TAGS_DETAIL_BY_CODES)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        try {
            if (!CollectionUtils.isEmpty(jsonObject.getJSONArray("tagCodes"))) {
                jsonObject.getJSONArray("tagCodes").forEach(item -> {
                    postClient.addParameter("tagCodes", String.valueOf(item));
                });
            }
        } catch (Exception e) {
            if(StringUtils.isNotEmpty(jsonObject.getString("tagCodes"))) {
                postClient.addParameter("tagCodes", jsonObject.getString("tagCodes"));
            }
        }
        return postClient.post();
    }
```