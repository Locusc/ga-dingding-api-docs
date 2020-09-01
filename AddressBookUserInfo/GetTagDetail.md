# 获取标签详情

## 接口说明
```java
    /**
     * 获取标签详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String employeeGetTagDetail(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2648)
## 实现方法
```java
    /**
     * 获取标签详情
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String employeeGetTagDetail(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadABUIApiConstants.ABUI_TAG_GET_TAG_DETAIL)
                .addParameter("tagCode", jsonObject.getString("tagCode"))
                .addParameter("tenantId", String.valueOf(jsonObject.getLong("tenantId")));
        return postClient.post();
    }
```