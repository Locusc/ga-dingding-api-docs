# 添加水印模板

## 接口说明
```java
    /**
     * 添加水印模板
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipWaterMarkTemplateSave(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2567)
## 实现方法
```java
    /**
     * 添加水印模板
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipWaterMarkTemplateSave(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadWaterMarkConstants.BIP_WATERMARK_TEMPLATE_SAVE)
                .addParameter("position", jsonObject.getString("position"))
                .addParameter("xDistance", String.valueOf(jsonObject.getDouble("xDistance")))
                .addParameter("yDistance", String.valueOf(jsonObject.getDouble("yDistance")))
                .addParameter("templateType", String.valueOf(jsonObject.getInteger("templateType")))
                .addParameter("isDefault", String.valueOf(jsonObject.getInteger("isDefault")))
                .addParameter("contentsJson", jsonObject.getString("contentsJson"));
        return postClient.post();
    }
```
