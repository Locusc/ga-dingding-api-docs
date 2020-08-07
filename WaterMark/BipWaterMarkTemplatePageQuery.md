# 水印模板分页查询

## 接口说明
```java
    /**
     * 水印模板分页查询
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipWaterMarkTemplatePageQuery(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2565)
## 实现方法
```java
    /**
     * 水印模板分页查询
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipWaterMarkTemplatePageQuery(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadWaterMarkConstants.BIP_WATERMARK_TEMPLATE_PAGE_QUERY)
                .addParameter("pageSize", jsonObject.getString("pageSize"))
                .addParameter("pageNum", jsonObject.getString("pageNum"));
        return postClient.post();
    }
```
