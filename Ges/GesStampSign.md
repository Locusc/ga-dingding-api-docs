# 签署盖章

## 接口说明
```java
    /**
     * 签署盖章
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String gesStampSign(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2555)
## 实现方法
```java
    /**
     * 签署盖章
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String gesStampSign(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadGESConstants.GES_STAMP_SIGN)
                .addParameter("signPositions", jsonObject.getString("signPositions"))
                .addParameter("sealKeeperId", jsonObject.getString("sealKeeperId"))
                .addParameter("verifyCode", jsonObject.getString("verifyCode"))
                .addParameter("essp", jsonObject.getString("essp"))
                .addParameter("businessId", jsonObject.getString("businessId"))
                .addParameter("fileBase64Code", jsonObject.getString("fileBase64Code"));
        return postClient.post();
    }
```