# 根据id查询点赞

## 接口说明
```java
    /**
     * 根据id查询点赞
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipLikeGet(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2553)
## 实现方法
```java
    /**
     * 根据id查询点赞
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipLikeGet(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadCommentsConstants.BIP_LIKE_GET)
                .addParameter("id", String.valueOf(jsonObject.getLong("id")));
        return postClient.post();
    }
```
