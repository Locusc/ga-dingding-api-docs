# 启用/停用标签

## 接口说明
```java
    /**
     * 启用/停用标签
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeUpdateTagStatus(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2653)
## 实现方法
```java
    /**
     * 启用/停用标签
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeUpdateTagStatus(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_TAG_UPDATE_TAG_STATUS)
                .addParameter("tagCode", jsonObject.getString("tagCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("operator", jsonObject.getString("operator"))
                .addParameter("status", jsonObject.getString("status"));
        return postClient.post();
    }
```