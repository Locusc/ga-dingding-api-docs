# 获取印章列表

## 接口说明
```java
    /**
     * 获取印章列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String gesQuerySeals(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2558)
## 实现方法
```java
    /**
     * 获取印章列表
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String gesQuerySeals(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadGESConstants.GES_QUERY_SEALS)
                .addParameter("organizationId", jsonObject.getString("organizationId"))
                .addParameter("sealKeeperId", jsonObject.getString("sealKeeperId"))
                .addParameter("essp", jsonObject.getString("essp"));
        return postClient.post();
    }
```