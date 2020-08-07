# 根据条件删除评论

## 接口说明
```java
    /**
     * 根据条件删除评论
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipCommentDeleteByConditions(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2547)
## 实现方法
```java
    /**
     * 根据条件删除评论
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipCommentDeleteByConditions(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_COMMENT_DELETE_BY_CONDITIONS)
                .addParameter("subjectId", jsonObject.getString("subjectId"))
                .addParameter("commentAccountId", String.valueOf(jsonObject.getLong("commentAccountId")))
                .addParameter("commentAccountTenantId", String.valueOf(jsonObject.getLong("commentAccountTenantId")))
                .addParameter("subjectAccountId", String.valueOf(jsonObject.getLong("subjectAccountId")))
                .addParameter("subjectAccountTenantId", String.valueOf(jsonObject.getLong("subjectAccountTenantId")))
                .addParameter("type", String.valueOf(jsonObject.getInteger("type")))
                .addParameter("bizCode", jsonObject.getString("bizCode"))
                .addParameter("id", String.valueOf(jsonObject.getLong("id")))
                .addParameter("isRecursion", jsonObject.getString("isRecursion"));
        return postClient.post();
    }
```