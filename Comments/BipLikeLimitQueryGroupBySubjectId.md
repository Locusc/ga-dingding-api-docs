# 根据不同条件查询点赞,并限制返回数量,根据主题id分类

## 接口说明
```java
    /**
     * 根据不同条件查询点赞,并限制返回数量，根据主题id分类
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipLikeLimitQueryGroupBySubjectId(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2551)
## 实现方法
```java
    /**
     * 根据不同条件查询点赞,并限制返回数量，根据主题id分类
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipLikeLimitQueryGroupBySubjectId(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_LIKE_LIMIT_QUERY_GROUP_BY_SUBJECT_ID)
                .addParameter("sortBy", jsonObject.getString("sortBy"))
                .addParameter("subjectId", jsonObject.getString("subjectId"))
                .addParameter("subjectIdStr", jsonObject.getString("subjectIdStr"))
                .addParameter("likeAccountId", String.valueOf(jsonObject.getLong("likeAccountId")))
                .addParameter("likeAccountTenantId", String.valueOf(jsonObject.getLong("likeAccountTenantId")))
                .addParameter("subjectAccountId", String.valueOf(jsonObject.getLong("subjectAccountId")))
                .addParameter("subjectAccountTenantId", String.valueOf(jsonObject.getLong("subjectAccountTenantId")))
                .addParameter("bizCode", jsonObject.getString("bizCode"))
                .addParameter("subjectKeyword", jsonObject.getString("subjectKeyword"))
                .addParameter("limitPerSubject", String.valueOf(jsonObject.getInteger("limitPerSubject")));
        return postClient.post();
    }
```
