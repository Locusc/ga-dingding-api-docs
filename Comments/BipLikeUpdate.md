# 更新点赞

## 接口说明
```java
    /**
     * 更新点赞
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipLikeUpdate(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2549)
## 实现方法
```java
    /**
     * 更新点赞
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipLikeUpdate(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_LIKE_UPDATE)
                .addParameter("id", String.valueOf(jsonObject.getLong("id")))
                .addParameter("extendedField", jsonObject.getString("extendedField"))
                .addParameter("subjectKeyword", jsonObject.getString("subjectKeyword"));
        return postClient.post();
    }
```
