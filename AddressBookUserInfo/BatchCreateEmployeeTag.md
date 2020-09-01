# 批量新增人员标签

## 接口说明
```java
    /**
     * 批量新增人员标签
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeBatchCreateEmployeeTag(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2656)
## 实现方法
```java
    /**
     * 批量新增人员标签
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeBatchCreateEmployeeTag(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_BATCH_CREATE_EMP_TAG)
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("operator", jsonObject.getString("operator"));
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
        try {
            if (!CollectionUtils.isEmpty(jsonObject.getJSONArray("employeeCodes"))) {
                jsonObject.getJSONArray("employeeCodes").forEach(item -> {
                    postClient.addParameter("employeeCodes", String.valueOf(item));
                });
            }
        } catch (Exception e) {
            if(StringUtils.isNotEmpty(jsonObject.getString("employeeCodes"))) {
                postClient.addParameter("employeeCodes", jsonObject.getString("employeeCodes"));
            }
        }
        return postClient.post();
    }
```