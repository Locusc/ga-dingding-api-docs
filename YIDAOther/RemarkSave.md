# 增加评论

## 接口说明
```java
    /**
     * 增加评论
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String yiDaRemarkSave(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2576)
## 实现方法
```java
     /** 增加评论
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String yiDaRemarkSave(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadYIDAOtherConstants.YIDA_REMARK_SAVE)
                .addParameter("appType", jsonObject.getString("appType"))
                .addParameter("formInstId", jsonObject.getString("formInstId"))
                .addParameter("replyId", String.valueOf(jsonObject.getLong("replyId")))
                .addParameter("systemToken", jsonObject.getString("systemToken"))
                .addParameter("language", jsonObject.getString("language"))
                .addParameter("atUserId", jsonObject.getString("atUserId"))
                .addParameter("userId", jsonObject.getString("userId"))
                .addParameter("content", jsonObject.getString("content"));
        return postClient.post();
    }
```