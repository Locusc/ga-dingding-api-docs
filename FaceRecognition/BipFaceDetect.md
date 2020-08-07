# 人脸检测

## 接口说明
```java
    /**
     * 人脸检测
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipFaceDetect(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2569)
## 实现方法
```java
    /**
     * 人脸检测
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipFaceDetect(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadFaceRecognitionConstants.BIP_FACE_DETECT)
                .addParameter("type", String.valueOf(jsonObject.getInteger("type")))
                .addParameter("imgUrl", jsonObject.getString("imgUrl"))
                .addParameter("imgBase64", jsonObject.getString("imgBase64"))
                .addParameter("isSave", jsonObject.getString("isSave"))
                .addParameter("employeeCode", jsonObject.getString("employeeCode"));
        return postClient.post();
    }
```