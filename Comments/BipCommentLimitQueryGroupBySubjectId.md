# 根据不同条件查询评论/回复评论,并限制返回数量,根据主题id分组返回

## 接口说明
```java
    /**
     * 根据不同条件查询评论/回复评论,并限制返回数量,根据主题id分组返回
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipCommentLimitQueryGroupBySubjectId(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2544)
## 实现方法
```java
    /**
     * 根据不同条件查询评论/回复评论,并限制返回数量,根据主题id分组返回
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipCommentLimitQueryGroupBySubjectId(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_COMMENT_LIMIT_QUERY_GROUP_BY_SUBJECT_ID)
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
                .addParameter("limitPerSubject", String.valueOf(jsonObject.getInteger("limitPerSubject")));
        return postClient.post();
    }
```