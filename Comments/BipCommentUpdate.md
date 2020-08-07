# 更新评论/更新评论回复

## 接口说明
```java
    /**
     * 更新评论/更新评论回复
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipCommentUpdate(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2542)
## 实现方法
```java
    /**
     * 更新评论/更新评论回复
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipCommentUpdate(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_COMMENT_UPDATE)
                .addParameter("id", String.valueOf(jsonObject.getLong("id")))
                .addParameter("extendedField", jsonObject.getString("extendedField"));
        return postClient.post();
    }
```