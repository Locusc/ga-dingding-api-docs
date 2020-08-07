# 移动端获取水印模板

## 接口说明
```java
    /**
     * 移动端获取水印模板
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipWaterMarkTemplateQuery(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2562)
## 实现方法
```java
    /**
     * 移动端获取水印模板
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipWaterMarkTemplateQuery(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadWaterMarkConstants.BIP_WATERMARK_TEMPLATE_QUERY)
                .addParameter("templateId", String.valueOf(jsonObject.getInteger("templateId")));
        return postClient.post();
    }
```
