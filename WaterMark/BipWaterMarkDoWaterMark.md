# 制作水印

## 接口说明
```java
    /**
     * 制作水印
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipWaterMarkDoWaterMark(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2568)
## 实现方法
```java
    /**
     * 制作水印
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipWaterMarkDoWaterMark(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadWaterMarkConstants.BIP_WATERMARK_DO_WATERMARK)
                .addParameter("lastName", jsonObject.getString("lastName"))
                .addParameter("employeeCode", jsonObject.getString("employeeCode"))
                .addParameter("isDefault", String.valueOf(jsonObject.getInteger("isDefault")))
                .addParameter("isSave", String.valueOf(jsonObject.getInteger("isSave")))
                .addParameter("wmType", String.valueOf(jsonObject.getInteger("wmType")))
                .addParameter("fileType", String.valueOf(jsonObject.getInteger("fileType")))
                .addParameter("srcImgUrl", jsonObject.getString("srcImgUrl"))
                .addParameter("base64Img", jsonObject.getString("base64Img"))
                .addParameter("srcFile", jsonObject.getString("srcFile"))
                .addParameter("templateId", String.valueOf(jsonObject.getLong("templateId")));
        return postClient.post();
    }
```