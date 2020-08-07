# 根据条件删除点赞

## 接口说明
```java
    /**
     * 根据条件删除点赞
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipLikeDeleteByConditions(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2554)
## 实现方法
```java
    /**
     * 根据条件删除点赞
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipLikeDeleteByConditions(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_LIKE_DELETE_BY_CONDITIONS)
                .addParameter("subjectId", jsonObject.getString("subjectId"))
                .addParameter("likeAccountId", String.valueOf(jsonObject.getLong("likeAccountId")))
                .addParameter("likeAccountTenantId", String.valueOf(jsonObject.getLong("likeAccountTenantId")))
                .addParameter("subjectAccountId", String.valueOf(jsonObject.getLong("subjectAccountId")))
                .addParameter("subjectAccountTenantId", String.valueOf(jsonObject.getLong("subjectAccountTenantId")))
                .addParameter("bizCode", jsonObject.getString("bizCode"))
                .addParameter("id", String.valueOf(jsonObject.getLong("id")));
        return postClient.post();
    }
```
