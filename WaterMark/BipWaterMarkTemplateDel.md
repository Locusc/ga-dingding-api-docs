# 删除水印模板

## 接口说明
```java
    /**
     * 删除水印模板
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipWaterMarkTemplateDel(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2564)
## 实现方法
```java
    /**
     * 删除水印模板
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipWaterMarkTemplateDel(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadWaterMarkConstants.BIP_WATERMARK_TEMPLATE_PAGE_QUERY);
        if(!CollectionUtils.isEmpty(jsonObject.getJSONArray("templateIds"))) {
            jsonObject.getJSONArray("templateIds").forEach(id -> {
                postClient.addParameter("templateIds", String.valueOf(id));
            });
        } else {
            postClient.addParameter("templateIds", jsonObject.getString("templateIds"));
        }
        return postClient.post();
    }
```
