# 压缩图片,根据需要的字节大小,精度压缩

## 接口说明
```java
    /**
     * 压缩图片，根据需要的字节大小，精度压缩
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipFaceCompressForSize(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2573)
## 实现方法
```java
    /**
     * 压缩图片，根据需要的字节大小，精度压缩
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipFaceCompressForSize(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadFaceRecognitionConstants.BIP_FACE_COMPRESS_FOR_SIZE)
                .addParameter("type", String.valueOf(jsonObject.getInteger("type")))
                .addParameter("content", jsonObject.getString("content"))
                .addParameter("url", jsonObject.getString("url"))
                .addParameter("size", jsonObject.getString("size"))
                .addParameter("quality", jsonObject.getString("quality"));
        return postClient.post();
    }
```