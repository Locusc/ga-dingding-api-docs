# 验证签章验证码

## 接口说明
```java
    /**
     * 验证签章验证码
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String gesStampCheckVerifyCode(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2556)
## 实现方法
```java
    /**
     * 验证签章验证码
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String gesStampCheckVerifyCode(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadGESConstants.GES_STAMP_CHECK_VERIFY_CODE)
                .addParameter("sealKeeperId", jsonObject.getString("sealKeeperId"))
                .addParameter("verifyCode", jsonObject.getString("verifyCode"))
                .addParameter("essp", jsonObject.getString("essp"))
                .addParameter("businessId", jsonObject.getString("businessId"));
        return postClient.post();
    }
```