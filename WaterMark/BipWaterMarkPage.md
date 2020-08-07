# 获取云端保存的水印文件（分页）

## 接口说明
```java
    /**
     * 获取云端保存的水印文件（分页）
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    String bipWaterMarkPage(JSONObject jsonObject);
```
## 入参说明
[参考官方文档](https://openplatform-portal.dg-work.cn/#/doc-jsapi?apiType=serverapi&docKey=2563)
## 实现方法
```java
    /**
     * 获取云端保存的水印文件（分页）
     * @param jsonObject JSONObject入参
     * @return java.lang.String
     **/
    @Override
    public String bipWaterMarkPage(JSONObject jsonObject) {
        PostClient postClient = this.newGadPostClient(GadWaterMarkConstants.BIP_WATERMARK_PAGE)
                .addParameter("pageSize", String.valueOf(jsonObject.getInteger("pageSize")))
                .addParameter("pageNum", String.valueOf(jsonObject.getInteger("pageNum")))
                .addParameter("employeeCode", jsonObject.getString("employeeCode"));
        return postClient.post();
    }
```