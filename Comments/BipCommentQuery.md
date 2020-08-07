# 根据不同条件查询评论/回复评论

## 接口说明
```java
    /**
     * 根据不同条件查询评论/回复评论
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipCommentQuery(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2543)
## 实现方法
```java
    /**
     * 根据不同条件查询评论/回复评论
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipCommentQuery(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_COMMENT_QUERY)
                .addParameter("pageNo", String.valueOf(jsonObject.getInteger("pageNo")))
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("sortBy", jsonObject.getString("sortBy"))
                .addParameter("subjectId", jsonObject.getString("subjectId"))
                .addParameter("subjectIdStr", jsonObject.getString("subjectIdStr"))
                .addParameter("commentAccountId", String.valueOf(jsonObject.getLong("commentAccountId")))
                .addParameter("commentAccountTenantId", String.valueOf(jsonObject.getLong("commentAccountTenantId")))
                .addParameter("subjectAccountId", String.valueOf(jsonObject.getLong("subjectAccountId")))
                .addParameter("subjectAccountTenantId", String.valueOf(jsonObject.getLong("subjectAccountTenantId")))
                .addParameter("type", String.valueOf(jsonObject.getInteger("type")))
                .addParameter("bizCode", jsonObject.getString("bizCode"))
                .addParameter("isPage", String.valueOf(jsonObject.getInteger("isPage")));
        return postClient.post();
    }
```