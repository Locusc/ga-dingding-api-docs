# 创建标签组

## 接口说明
```java
    /**
     * 创建标签组
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeCreateTagGroup(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2646)
## 实现方法
```java
    /**
     * 创建标签组
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeCreateTagGroup(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_TAG_CREATE_TAG_GROUP)
                .addParameter("creator", jsonObject.getString("creator"))
                .addParameter("tagGroupDescription", jsonObject.getString("tagGroupDescription"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")))
                .addParameter("tagGroupName", jsonObject.getString("tagGroupName"));
        return postClient.post();
    }
```