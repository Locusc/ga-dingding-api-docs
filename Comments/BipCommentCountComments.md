# 根据条件查询评论数量

## 接口说明
```java
    /**
     * 根据条件查询评论数量
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipCommentCountComments(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2545)
## 实现方法
```java
    /**
     * 根据条件查询评论数量
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipCommentCountComments(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_COMMENT_COUNT_COMMENTS)
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
                .addParameter("bizCode", jsonObject.getString("bizCode"));
        return postClient.post();
    }
```