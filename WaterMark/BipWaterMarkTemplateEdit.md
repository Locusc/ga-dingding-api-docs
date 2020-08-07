# 修改水印模板

## 接口说明
```java
    /**
     * 修改水印模板
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipWaterMarkTemplateEdit(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2566)
## 实现方法
```java
    /**
     * 修改水印模板
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipWaterMarkTemplateEdit(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadWaterMarkConstants.BIP_WATERMARK_TEMPLATE_EDIT)
                .addParameter("position", jsonObject.getString("position"))
                .addParameter("xDistance", String.valueOf(jsonObject.getDouble("xDistance")))
                .addParameter("yDistance", String.valueOf(jsonObject.getDouble("yDistance")))
                .addParameter("templateType", String.valueOf(jsonObject.getInteger("templateType")))
                .addParameter("isDefault", String.valueOf(jsonObject.getInteger("isDefault")))
                .addParameter("contentsJson", jsonObject.getString("contentsJson"))
                .addParameter("templateId", String.valueOf(jsonObject.getLong("templateId")));
        return postClient.post();
    }
```
