# 根据不同条件查询点赞

## 接口说明
```java
    /**
     * 根据不同条件查询点赞
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipLikeQuery(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2550)
## 实现方法
```java
    /**
     * 根据不同条件查询点赞
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipLikeQuery(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_LIKE_QUERY)
                .addParameter("pageNo", String.valueOf(jsonObject.getInteger("pageNo")))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("sortBy", jsonObject.getString("sortBy"))
                .addParameter("subjectId", jsonObject.getString("subjectId"))
                .addParameter("subjectIdStr", jsonObject.getString("subjectIdStr"))
                .addParameter("likeAccountId", String.valueOf(jsonObject.getLong("likeAccountId")))
                .addParameter("likeAccountTenantId", String.valueOf(jsonObject.getLong("likeAccountTenantId")))
                .addParameter("subjectAccountId", String.valueOf(jsonObject.getLong("subjectAccountId")))
                .addParameter("subjectAccountTenantId", String.valueOf(jsonObject.getLong("subjectAccountTenantId")))
                .addParameter("bizCode", jsonObject.getString("bizCode"))
                .addParameter("isPage", String.valueOf(jsonObject.getInteger("isPage")))
                .addParameter("subjectKeyword", jsonObject.getString("subjectKeyword"));
        return postClient.post();
    }
```
