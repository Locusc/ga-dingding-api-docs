# 点赞

## 接口说明
```java
    /**
     * 点赞
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipLikeAdd(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2548)
## 实现方法
```java
    /**
     * 点赞
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipLikeAdd(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_LIKE_ADD)
                .addParameter("subjectId", jsonObject.getString("subjectId"))
                .addParameter("subjectAccountId", String.valueOf(jsonObject.getLong("subjectAccountId")))
                .addParameter("subjectAccountTenantId", String.valueOf(jsonObject.getLong("subjectAccountTenantId")))
                .addParameter("extendedField", jsonObject.getString("extendedField"))
                .addParameter("subjectKeyword", jsonObject.getString("subjectKeyword"));
        return postClient.post();
    }
```
