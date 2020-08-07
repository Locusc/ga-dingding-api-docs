# 人脸属性识别

## 接口说明
```java
    /**
     * 人脸属性识别
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipFaceAttribute(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2572)
## 实现方法
```java
    /**
     * 人脸属性识别
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipFaceAttribute(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadFaceRecognitionConstants.BIP_FACE_ATTRIBUTE)
                .addParameter("type", String.valueOf(jsonObject.getInteger("type")))
                .addParameter("imgUrl", jsonObject.getString("imgUrl"))
                .addParameter("imgBase64", jsonObject.getString("imgBase64"));
        return postClient.post();
    }
```