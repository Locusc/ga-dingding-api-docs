# 图片压缩,按照宽高压缩

## 接口说明
```java
    /**
     * 图片压缩，按照宽高压缩
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipFaceCompressForBorder(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2575)
## 实现方法
```java
    /**
     * 图片压缩，按照宽高压缩
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipFaceCompressForBorder(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadFaceRecognitionConstants.BIP_FACE_COMPRESS_FOR_BORDER)
                .addParameter("type", String.valueOf(jsonObject.getInteger("type")))
                .addParameter("content", jsonObject.getString("content"))
                .addParameter("url", jsonObject.getString("url"))
                .addParameter("width", jsonObject.getString("width"))
                .addParameter("height", jsonObject.getString("height"))
                .addParameter("force", jsonObject.getString("force"));
        return postClient.post();
    }
```