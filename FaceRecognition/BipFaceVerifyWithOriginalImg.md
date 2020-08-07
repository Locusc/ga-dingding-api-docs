# 人脸比对（上传两张图片比对）

## 接口说明
```java
    /**
     * 人脸比对（上传两张图片比对）
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipFaceVerifyWithOriginalImg(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2571)
## 实现方法
```java
    /**
     * 人脸比对（上传两张图片比对）
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipFaceVerifyWithOriginalImg(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadFaceRecognitionConstants.BIP_FACE_VERIFY_WITH_ORIGINAL_IMG)
                .addParameter("type", String.valueOf(jsonObject.getInteger("type")))
                .addParameter("imgUrl", jsonObject.getString("imgUrl"))
                .addParameter("originalImgUrl", jsonObject.getString("originalImgUrl"))
                .addParameter("imgBase64", jsonObject.getString("imgBase64"))
                .addParameter("originalImgBase64", jsonObject.getString("originalImgBase64"));
        return postClient.post();
    }
```