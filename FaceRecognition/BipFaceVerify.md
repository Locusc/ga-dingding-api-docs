# 人脸比对(服务端事先录入原图)

## 接口说明
```java
    /**
     * 人脸比对(服务端事先录入原图)
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipFaceVerify(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2570)
## 实现方法
```java
    /**
     * 人脸比对(服务端事先录入原图)
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipFaceVerify(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadFaceRecognitionConstants.BIP_FACE_VERIFY)
                .addParameter("type", String.valueOf(jsonObject.getInteger("type")))
                .addParameter("imgUrl", jsonObject.getString("imgUrl"))
                .addParameter("imgBase64", jsonObject.getString("imgBase64"))
                .addParameter("employeeCode", jsonObject.getString("employeeCode"))
                .addParameter("bizCode", jsonObject.getString("bizCode"));
        return postClient.post();
    }
```