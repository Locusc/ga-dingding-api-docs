# 图片压缩,按照比例,精度压缩

## 接口说明
```java
    /**
     * 图片压缩，按照比例，精度压缩
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipFaceCompressForScale(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2574)
## 实现方法
```java
    /**
     * 图片压缩，按照比例，精度压缩
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipFaceCompressForScale(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadFaceRecognitionConstants.BIP_FACE_COMPRESS_FOR_SCALE)
                .addParameter("type", String.valueOf(jsonObject.getInteger("type")))
                .addParameter("content", jsonObject.getString("content"))
                .addParameter("url", jsonObject.getString("url"))
                .addParameter("accuracy", jsonObject.getString("accuracy"))
                .addParameter("quality", jsonObject.getString("quality"));
        return postClient.post();
    }
```