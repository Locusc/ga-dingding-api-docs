# 发送签章验证码

## 接口说明
```java
    /**
     * 发送签章验证码
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String gesStampSendVerifyCode(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2557)
## 实现方法
```java
    /**
     * 发送签章验证码
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String gesStampSendVerifyCode(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadGESConstants.GES_STAMP_SEND_VERIFY_CODE)
                .addParameter("sealKeeperId", jsonObject.getString("sealKeeperId"))
                .addParameter("essp", jsonObject.getString("essp"))
                .addParameter("businessId", jsonObject.getString("businessId"));
        return postClient.post();
    }
```