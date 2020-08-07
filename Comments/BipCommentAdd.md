# 评论/评论回复

## 接口说明
```java
    /**
     * 评论/评论回复
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipCommentAdd(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2541)
## 实现方法
```java
    /**
     * 评论/评论回复
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipCommentAdd(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_COMMENT_ADD)
                .addParameter("subjectId", jsonObject.getString("subjectId"))
                .addParameter("type", jsonObject.getString("type"))
                .addParameter("replyCommentId", jsonObject.getString("replyCommentId"))
                .addParameter("content", jsonObject.getString("content"))
                .addParameter("subjectAccountId", jsonObject.getString("subjectAccountId"))
                .addParameter("subjectAccountTenantId", jsonObject.getString("subjectAccountTenantId"))
                .addParameter("extendedField", jsonObject.getString("extendedField"));
        return postClient.post();
    }
```