# 根据评论id查询评论

## 接口说明
```java
    /**
     * 根据评论id查询评论
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipCommentGet(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2546)
## 实现方法
```java
    /**
     * 根据评论id查询评论
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipCommentGet(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_COMMENT_GET)
                .addParameter("id", String.valueOf(jsonObject.getLong("id")));
        return postClient.post();
    }
```