# 获取群成员

## 接口说明
```java
    /**
     * 获取群成员
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String chatGroupGetUsers(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2604)
## 实现方法
```java
    /**
     * 获取群成员
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String chatGroupGetUsers(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadChatApiConstants.CHAT_GROUP_GET_USERS)
                .addParameter("chatId", jsonObject.getString("chatId"));
        return postClient.post();
    }
```