# 根据条件查询点赞数量

## 接口说明
```java
    /**
     * 根据条件查询点赞数量
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipLikeCountLike(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2552)
## 实现方法
```java
    /**
     * 根据条件查询点赞数量
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipLikeCountLike(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_LIKE_COUNT_LIKE)
                .addParameter("sortBy", jsonObject.getString("sortBy"))
                .addParameter("subjectId", jsonObject.getString("subjectId"))
                .addParameter("likeAccountId", String.valueOf(jsonObject.getLong("likeAccountId")))
                .addParameter("likeAccountTenantId", String.valueOf(jsonObject.getLong("likeAccountTenantId")))
                .addParameter("subjectAccountId", String.valueOf(jsonObject.getLong("subjectAccountId")))
                .addParameter("subjectAccountTenantId", String.valueOf(jsonObject.getLong("subjectAccountTenantId")))
                .addParameter("bizCode", jsonObject.getString("bizCode"))
                .addParameter("subjectKeyword", jsonObject.getString("subjectKeyword"));
        return postClient.post();
    }
```
